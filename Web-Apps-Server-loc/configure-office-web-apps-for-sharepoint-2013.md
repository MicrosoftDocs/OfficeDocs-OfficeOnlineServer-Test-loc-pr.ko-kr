---
title: SharePoint 2013용 Office Web Apps 구성
TOCTitle: SharePoint 2013용 Office Web Apps 구성
ms:assetid: a5276781-133b-413c-beca-b851e17c2081
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Ff431687(v=office.15)
ms:contentKeyID: 49643409
ms.date: 12/21/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# SharePoint 2013용 Office Web Apps 구성

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2016-12-16_

**요약:** Office Web Apps를 사용하도록 SharePoint 2013을 구성하는 방법을 설명합니다.

**대상:** IT 전문가

이 문서에서는 [Office Web Apps 서버 배포](deploy-office-web-apps-server.md)가 중지된 위치를 알아냅니다. 또한 Office Web Apps 서버 실행 서버를 설정하고, Office Web Apps 서버를 사용하도록 SharePoint 2013을 구성합니다. 이렇게 하려면 먼저 SharePoint 2013에서 일부 Windows PowerShell cmdlet을 실행해야 합니다. 그러면 사용자가 브라우저의 SharePoint 2013 문서 라이브러리에서 Office 파일을 열 수 있습니다.

Office Web Apps 서버의 기능을 잘 모르는 경우 [개요 항목을 확인](office-web-apps-server-overview.md)하세요.

이 문서의 내용

  - Office Web Apps 서버를 사용하도록 SharePoint 2013을 구성하기 전에

  - Office Web Apps 서버를 사용하도록 SharePoint 2013 구성

  - SharePoint 2013에서 사용 시 Office Web Apps 오류 해결

  - Office Web Apps 서버에서 SharePoint 2013 연결 끊기

## Office Web Apps 서버를 사용하도록 SharePoint 2013을 구성하기 전에

시작하기 전에 확인해야 할 사항

  - SharePoint 2013을 설치합니다. 지침은 [SharePoint 2013 설치](https://technet.microsoft.com/ko-kr/library/cc303424\(v=office.15\))를 참조하세요.

  - 모든 SharePoint 2013 웹 응용 프로그램이 클레임 기반 인증을 사용하는지 확인합니다. Office Web Apps 렌더링 및 편집 기능은 클래식 모드 인증을 사용하는 SharePoint 2013 웹 응용 프로그램에서 작동하지 않습니다. 자세한 내용은 [Office Web Apps에 대한 SharePoint 인증 요구 사항](plan-office-web-apps-used-with-sharepoint-2013.md)에서 알아보세요.

  - 사용자가 웹 브라우저에서 Office 문서를 읽는 것뿐만 아니라 편집도 할 수 있도록 설정하려면 편집 라이선스가 필요합니다. 또한 Office Web Apps 서버 팜에서 편집을 사용하도록 설정해야 합니다. 라이선스 요구 사항에 대한 자세한 내용은 [Office 파일 편집을 위해 Office Web Apps 라이선스 적용](plan-office-web-apps-used-with-sharepoint-2013.md)에서 확인할 수 있습니다.

  - 시스템 계정을 사용하여 SharePoint 2013에 로그온하는 경우 SharePoint 2013과 Office Web Apps 서버 간의 연결을 테스트할 수 없습니다. 그러므로 연결을 테스트하려면 다른 계정을 사용하여 로그온합니다.

  - 메모리 부족 현상이 발생하면 Office Web Apps에서 Office 문서를 미리 보지 못할 수 있습니다. SharePoint 2013에 대한 [하드웨어 요구 사항 - 웹 서버, 응용 프로그램 서버 및 단일 서버 설치](https://technet.microsoft.com/ko-kr/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver) 문서를 검토하세요. Office Web Apps 서버에서 사용되는 것과 동일한 요구 사항이 나와 있습니다.

## Office Web Apps 서버를 사용하도록 SharePoint 2013 구성

HTTP를 사용할지, HTTPS를 사용할지에 따라 다음 섹션 중 하나를 선택합니다. HTTP는 일반적으로 테스트 환경에서만 권장됩니다. 프로덕션 환경에서는 안전성이 향상된 HTTPS 프로토콜을 사용하는 것이 더 바람직합니다.

## HTTP를 사용하는 테스트 환경

이 구성의 경우 [테스트 환경에서 단일 서버 Office Web Apps 서버 팜 배포](deploy-office-web-apps-server.md)의 단계를 수행하여 Office Web Apps 서버를 설정했는지 확인합니다. Office Web Apps 서버 팜은 내부 URL 및 HTTP를 사용하도록 구성해야 합니다. [비디오: SharePoint 2013용 Office Web Apps 구성](video-configure-office-web-apps-for-sharepoint-2013.md)에는 Office Web Apps 서버를 설정하고 테스트 환경에서 Office Web Apps 서버를 사용하도록 SharePoint 2013을 구성하는 방법이 나와 있습니다.

## 1단계: 관리자 권한 SharePoint 2013 관리 셸 열기

사용 중인 서버 운영 체제에 해당하는 절차를 선택합니다.

**Windows Server 2008 R2**

1.  **시작** \> **모든 프로그램** \> **Microsoft SharePoint 2013 제품**을 클릭합니다.

2.  **SharePoint 2013 관리 셸**을 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 클릭합니다.

**Windows Server 2012**

1.  Windows 로고 키와 Q를 동시에 누르거나, 화면 모서리에서 살짝 밀어 참을 표시한 다음 **검색**을 클릭하여 컴퓨터에 설치되어 있는 모든 응용 프로그램을 표시합니다.

2.  **SharePoint 2013 관리 셸**을 마우스 오른쪽 단추로 클릭하여 앱 바를 표시합니다.

3.  앱 바에서 **관리자 권한으로 실행**을 클릭합니다.

## 2단계: SharePoint 2013과 Office Web Apps 서버 간에 바인딩 만들기

다음 명령을 실행합니다. 여기서 \<WacServerName\>은 내부 URL에 설정한 URL의 FQDN(정규화된 도메인 이름)입니다. 이 명령은 Office Web Apps 서버 트래픽의 진입점입니다. 이 테스트 환경에서는 –AllowHTTP 매개 변수를 지정함으로써 SharePoint 2013이 HTTP를 사용하여 Office Web Apps 서버 팜에서 검색 정보를 수신하도록 허용해야 합니다. –AllowHTTP를 지정하지 않으면 SharePoint 2013에서 Office Web Apps 서버 팜과 통신하는 데 HTTPS를 사용하려고 하며, 이 명령에도 실패합니다.

    New-SPWOPIBinding -ServerName <WacServerName> -AllowHTTP

이 명령을 실행하면 Windows PowerShell 명령 프롬프트에 바인딩 목록이 표시됩니다.

도움이 필요하면 [New-SPWOPIBinding](new-spwopibinding.md)을 참조하세요.

## 3단계: SharePoint 바인딩에 대한 WOPI 영역 확인

Office Web Apps 서버에서는 영역을 사용하여 호스트(이 경우 SharePoint 2013)와 통신할 때 사용할 URL(내부/외부) 및 프로토콜(HTTP/HTTPS)을 결정합니다. 기본적으로 SharePoint Server 2013은 **internal-https** 영역을 사용합니다. 다음 명령을 실행하여 이 영역이 현재 영역인지 확인합니다.

    Get-SPWOPIZone

이 명령에 따라 표시되는 WOPI 영역은 **internal-http**여야 합니다. 이 영역이 제대로 표시되면 5단계로 건너뛰고, 제대로 표시되지 않으면 다음 단계를 참조하세요.

도움이 필요하면 [Get-SPWOPIZone](get-spwopizone.md)을 참조하세요.

## 4단계: WOPI 영역을 internal-http로 변경

3단계의 결과가 **internal-https**였다면 다음 명령을 실행하여 영역을 **internal-http**로 변경합니다. SharePoint 2013의 영역은 Office Web Apps 서버 팜의 영역과 일치해야 하므로 이와 같이 변경해야 합니다.

    Set-SPWOPIZone -zone "internal-http"

**Get-SPWOPIZone**을 다시 실행하여 새 영역이 **internal-http**인지 확인합니다.

도움이 필요하면 [Set-SPWOPIZone](set-spwopizone.md) 및 [Get-SPWOPIZone](get-spwopizone.md)을 참조하세요.

## 5단계: SharePoint 2013에서 AllowOAuthOverHttp 설정을 True로 변경

테스트 환경에서 HTTP를 통해 SharePoint 2013과 함께 Office Web Apps를 사용하려면 AllowOAuthOverHttp를 **True**로 설정해야 합니다. 그렇지 않으면 Office Web Apps가 작동하지 않습니다. 다음 예제를 실행하여 현재 상태를 확인할 수 있습니다.

    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp

이 명령이 **False**를 반환하면 다음 명령을 실행하여 **True**로 설정합니다.

```
    $config = (Get-SPSecurityTokenServiceConfig)
```
```
    $config.AllowOAuthOverHttp = $true
```
```
    $config.Update()
```

다음 명령을 다시 실행하여 AllowOAuthOverHttp 설정이 현재 **True**로 설정되어 있는지 확인합니다.

    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp

도움이 필요하면 [Get-SPSecurityTokenServiceConfig](https://technet.microsoft.com/ko-kr/library/ff607642\(v=office.15\))을 참조하세요.

## 6단계: Office Web Apps가 작동하는지 확인

SharePoint 2013에서 Office Web Apps로 문서를 편집하거나 볼 수 없으면 시스템 계정으로 로그온되어 있지는 않은지 확인합니다. Office 문서가 포함된 SharePoint 2013 문서 라이브러리로 이동하여 Word, PowerPoint, Excel 또는 OneNote 파일을 확인합니다. 해당 문서가 Office Web Apps를 사용하여 파일을 표시하는 브라우저에서 열려야 합니다.

이 단계가 실패하면 Office Web Apps에서 오류 해결을 참조하세요.

## HTTPS를 사용하는 프로덕션 환경

다음 절차를 시작하기 전에 [HTTPS를 사용하는 단일 서버 Office Web Apps 서버 팜 배포](e4d51dc4-6460-437d-aa8e-0ae4d3aa8cc5\(office.15\)#singlehttps) 또는 [HTTPS를 사용하는 부하 분산된 다중 서버 Office Web Apps 서버 팜 배포](e4d51dc4-6460-437d-aa8e-0ae4d3aa8cc5\(office.15\)#multihttps)의 단계를 수행하여 Office Web Apps 서버를 설정했는지 확인합니다.

## 1단계: SharePoint 2013 관리 셸 열기

사용 중인 서버 운영 체제에 해당하는 절차를 선택합니다.

**Windows Server 2008 R2**

1.  **시작** \> **모든 프로그램** \> **Microsoft SharePoint 2013 제품**을 선택합니다.

2.  **SharePoint 2013 관리 셸**을 마우스 오른쪽 단추로 클릭하여 바로 가기 메뉴를 표시한 다음 **관리자 권한으로 실행**을 클릭합니다.

**Windows Server 2012**

1.  Windows 로고 키와 Q를 동시에 누르거나, 화면 모서리에서 살짝 밀어 참을 표시한 다음 **검색**을 클릭하여 컴퓨터에 설치되어 있는 모든 응용 프로그램을 표시합니다.

2.  **SharePoint 2013 관리 셸**을 마우스 오른쪽 단추로 클릭하여 앱 바를 표시합니다.

3.  앱 바에서 **관리자 권한으로 실행**을 클릭합니다.

## 2단계: SharePoint 2013과 Office Web Apps 서버 간에 바인딩 만들기

다음 명령을 실행합니다. 여기서 \<WacServerName\>은 내부 URL에 설정한 URL의 FQDN(정규화된 도메인 이름)입니다. 이 명령은 Office Web Apps 서버 트래픽의 진입점입니다.

    New-SPWOPIBinding -ServerName <WacServerName> 

도움이 필요하면 [New-SPWOPIBinding](new-spwopibinding.md)을 참조하세요.

## 3단계: SharePoint 2013의 WOPI 영역 확인

Office Web Apps 서버에서는 영역을 사용하여 호스트(이 경우 SharePoint 2013)와 통신할 때 사용할 URL(내부/외부) 및 프로토콜(HTTP/HTTPS)을 결정합니다. 기본적으로 SharePoint Server 2013은 **internal-https** 영역을 사용합니다. 다음 명령을 실행하여 이 영역이 현재 영역인지 확인합니다.

    Get-SPWOPIZone

표시되는 WOPI 영역을 적어 둡니다.

도움이 필요하면 [Get-SPWOPIZone](get-spwopizone.md)을 참조하세요.

## 4단계: 필요한 경우 WOPI 영역 변경

환경에 따라 WOPI 영역을 변경해야 할 수 있습니다. 내부/외부용으로 모두 사용되는 SharePoint 팜이 있는 경우 외부를 지정하고, 내부 전용 SharePoint 팜이 있는 경우에는 내부를 지정합니다.

3단계의 결과가 **internal-https**로 표시되고 SharePoint 팜이 내부 전용이면 이 단계를 건너뛰어도 됩니다. 내부와 외부에서 모두 사용되는 SharePoint 팜이 있는 경우에는 다음 명령을 실행하여 영역을 **external-https**로 변경해야 합니다.

    Set-SPWOPIZone -zone "external-https"

도움이 필요하면 [Set-SPWOPIZone](set-spwopizone.md)을 참조하세요.

## 5단계: Office Web Apps가 작동하는지 확인

SharePoint 2013에서 Office Web Apps로 문서를 편집하거나 볼 수 없으면 시스템 계정으로 로그온되어 있지는 않은지 확인합니다. Office 문서가 포함된 SharePoint 2013 문서 라이브러리로 이동하여 Word, PowerPoint, Excel 또는 OneNote 파일을 확인합니다. 해당 문서가 Office Web Apps를 사용하여 파일을 표시하는 브라우저에서 열려야 합니다.

이 단계가 실패하면 Office Web Apps에서 오류 해결을 참조하세요.

## SharePoint 2013에서 Office Web Apps 사용 시 오류 해결

Office Web Apps가 SharePoint 2013과 함께 사용할 때 정상적으로 작동하지 않으면 아래에서 증상을 찾은 다음 제목을 확장하여 문제 해결 단계를 확인합니다.

## 문제: SharePoint 라이브러리에서 "새 문서" 링크를 선택하면 새 Office 문서를 만드는 옵션이 표시되는 대신 문서를 업로드하라는 메시지가 표시됩니다. 이때 Office 문서를 한 번 클릭하여 선택하면 파일이 클라이언트 응용 프로그램에서 열립니다. Office 문서 미리 보기는 표시되지 않습니다.

다음과 같은 문제 해결 옵션을 사용해 볼 수 있습니다.

**새 문서를 만드는 데 사용하는 SharePoint 웹 응용 프로그램에서 클레임 기반 인증을 사용하는지 확인**

클레임 기반 인증을 사용하는 웹 응용 프로그램만 Office Web Apps에서 파일을 열 수 있습니다. 웹 응용 프로그램에 대한 인증 공급자를 확인하려면 다음 단계를 수행합니다.

1.  SharePoint 2013 중앙 관리에서 **웹 응용 프로그램 관리**를 클릭합니다.

2.  확인하려는 웹 응용 프로그램을 선택하고 리본 메뉴에서 **인증 공급자**를 클릭합니다.

인증 공급자가 **클레임 기반 인증**으로 표시되어야 Office Web Apps가 웹 응용 프로그램에서 정상적으로 작동합니다. 이 문제를 해결하려면 웹 응용 프로그램을 삭제한 후 클레임 기반 인증을 사용하여 다시 만들거나, 웹 응용 프로그램의 인증 방법을 변경하면 됩니다. 자세한 내용은 [Office Web Apps에 대한 SharePoint 인증 요구 사항](plan-office-web-apps-used-with-sharepoint-2013.md)에서 확인할 수 있습니다.

**SharePoint 2013과 Office Web Apps 서버 팜에서 WOPI 영역이 일치하는지 확인**

이 작업을 수행하려면 SharePoint Server에서 다음 명령을 실행합니다.

    Get-SPWopiZone 

결과는 다음 중 하나입니다.

  - internal-https

  - internal-http

  - external-https

  - external-http

그런 다음 SharePoint Server에서 아래 명령을 실행합니다.

    Get-SPWOPIBinding

출력에서 **WopiZone: *영역***을 찾습니다. Get-SPWopiZone의 결과가 Get-SPWOPIBinding에서 반환되는 영역과 일치하지 않으면 SharePoint Server에서 **Set-SPWOPIZone -Zone** cmdlet을 실행하여Get-SPWOPIBinding의 결과와 일치하도록 WOPI 영역을 변경합니다. 이러한 cmdlet을 사용하는 방법에 대한 도움말은 [Get-SPWOPIBinding](get-spwopibinding.md), [Set-SPWOPIBinding](set-spwopibinding.md) 및 [Get-SPWOPIZone](get-spwopizone.md)을 참조하세요.

## 문제: Office Web Apps에서 Office 문서를 편집하려고 하면 "죄송합니다. 이 문서는 편집용으로 열 수 없습니다."라는 오류가 표시됩니다.

경우에 따라 AD(Active Directory) 보안 그룹의 구성원인 사용자가 브라우저에서 문서를 편집하지 못할 수 있습니다. 이 경우 UPA(User Profile Service 응용 프로그램)가 제대로 구성되어 있고, 사용자 및 그룹 구성원과 완전히 동기화되어 있는지 확인해야 합니다. 자세한 내용은 KB 문서 [SharePoint 2013에서 보안 그룹의 구성원인 사용자로 Office Web Apps 2013 파일을 편집할 수 없음](https://support.microsoft.com/kb/2908321?ln=ko-kr)을 참조하세요.

## 문제: Office Web Apps에서 Office 문서를 보려고 하면 "죄송합니다. 문제가 발생했습니다."라는 오류가 표시됩니다.

문서를 편집하거나 볼 수 없으면 시스템 계정으로 로그인되어 있지는 않은지 확인합니다. 다른 사용자로 로그온한 다음 Office Web Apps에 다시 액세스해 보세요.

## 문제: Office Web Apps에서 Office 문서를 보려고 하면 "죄송합니다. 문제가 발생하여 이 문서를 열 수 없습니다."라는 오류가 표시됩니다.

HTTP를 사용하는 테스트 환경에서 Office Web Apps를 설정한 경우 5단계: SharePoint 2013에서 AllowOAuthOverHttp 설정을 True로 변경에 설명된 바와 같이 AllowOAuthOverHttp 설정을 **True**로 설정했는지 확인합니다.

[New-OfficeWebAppsHost](new-officewebappshost.md) cmdlet을 사용하여 허용 목록에 도메인을 추가한 적이 있다면 허용 목록에 있는 호스트 도메인에서 Office Web Apps에 액세스하고 있는지 확인하세요. 허용 목록의 호스트 도메인을 보려면 Office Web Apps 서버에서 관리자 권한으로 Windows PowerShell 프롬프트를 열고 [Get-OfficeWebAppsHost](get-officewebappshost.md) cmdlet을 실행합니다. 허용 목록에 도메인을 추가하려면 [New-OfficeWebAppsHost](new-officewebappshost.md) cmdlet을 사용합니다.

## 문제: Office Web Apps에서 Office 문서를 보려고 하면 "죄송합니다. 서비스 사용량이 많아 Word Web App에서 이 문서를 열 수 없습니다. 나중에 다시 시도하세요."라는 오류가 표시됩니다.

  - Office Web Apps 서버를 도메인 컨트롤러에 설치했습니까? Office Web Apps 서버는 도메인 컨트롤러에서 실행할 수 없습니다. 도메인에 속한 별도의 서버에 Office Web Apps 서버를 설치해야 합니다. 자세한 내용은 [Office Web Apps 서버의 소프트웨어, 하드웨어 및 구성 요구 사항](plan-office-web-apps-server.md)을 참조하세요.

  - SharePoint 2013 빌드 15.0.4420.1017 이상을 실행 중인지 확인합니다. SharePoint 2013 서버에서 다음 단계에 따라 빌드 번호를 확인하세요.
    
    1.  **시작** \> **모든 프로그램** \> **Microsoft SharePoint 2013 제품** \> **SharePoint 2013 중앙 관리**로 이동합니다.
    
    2.  **시스템 설정** \> **이 팜의 서버 관리**를 선택합니다.
    
    **구성 데이터베이스 버전**이 **15.0.4420.1017** 이상인지 확인합니다. 이 버전보다 낮으면 [Office, Office Server 및 관련 제품에 대한 업데이트 센터](https://go.microsoft.com/fwlink/p/?linkid=160585)에서 자세한 내용을 참조하세요.

## 문제: 사용자가 생성한 URL을 사용하여 Office Web Apps에서 Office 문서를 보려고 하면 "파일을 찾을 수 없습니다. 원본 파일의 URL이 올바르지 않거나 문서가 공개 액세스를 허용하지 않습니다. URL이 올바른지 확인한 다음 문서 소유자에게 문의하세요."라는 오류가 표시됩니다.

사용자가 생성한 URL에서 열려는 문서의 파일 크기가 10MB보다 큽니까? 문서가 10MB를 초과하지 않는지 확인하세요.

## 문제: Office 문서 미리 보기가 SharePoint 2013에 표시되지 않습니다. 대신 "이 콘텐츠를 프레임에 표시할 수 없습니다."라는 오류가 표시됩니다.

메모리 부족 현상이 발생하면 Office 문서 미리 보기에도 문제가 생길 수 있습니다. [하드웨어 요구 사항 - 웹 서버, 응용 프로그램 서버 및 단일 서버 설치](https://technet.microsoft.com/ko-kr/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver)에서 SharePoint 2013에 대한 메모리 요구 사항을 확인하세요. Office Web Apps 서버에서 사용되는 것과 동일한 요구 사항이 나와 있습니다.

## 문제: “데이터 연결이 항상 연결 파일을 사용하도록 설정되어 있고 {0:ExcelWebApp}에서 외부 연결 파일을 지원하지 않습니다. 다음의 데이터 연결을 새로 고치지 못했습니다.”라는 오류가 표시됩니다.

Office Web Apps 서버에서 데이터 연결 정보를 저장하는 ODC(Office 데이터 연결) 파일을 지원하지 않기 때문에 발생하는 오류입니다. 이 문제를 해결하려면 다음 단계를 수행하십시오.

1.  Excel 클라이언트 응용 프로그램에서 통합 문서를 엽니다.

2.  **데이터** \> **연결**을 클릭합니다.

3.  메시지에 나열된 데이터 연결을 선택한 다음 **속성**을 클릭합니다.

4.  **정의** 탭을 클릭합니다.

5.  **항상 연결 파일 사용** 확인란의 선택을 취소합니다.

6.  통합 문서를 SharePoint 문서 라이브러리에 다시 업로드합니다.

사용자가 데이터 모델 또는 Power View 보기가 포함된 통합 문서를 브라우저 창에서 사용할 수 있도록 하려면 통합 문서를 표시하도록 SharePoint Server의 Excel 서비스를 구성합니다. 이렇게 하려면 SharePoint 관리자가 SharePoint Server가 설치된 서버에서 New-SPWOPISupressionSetting cmdlet을 실행해야 합니다. 자세한 내용은 [New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md) 및 [SharePoint Server 2013에서 Excel Services 관리](https://technet.microsoft.com/ko-kr/library/ee681487\(v=office.15\))를 참조하십시오.

## Office Web Apps 서버에서 SharePoint 2013 연결 끊기

어떤 이유로든 Office Web Apps 서버에서 SharePoint 2013 연결을 끊으려면 다음 명령 예제를 사용합니다.

    Remove-SPWOPIBinding -All:$true

도움이 필요하면 [Remove-SPWOPIBinding](remove-spwopibinding.md)을 참조하십시오.

## 참고 항목


[New-SPWOPIBinding](new-spwopibinding.md)  
[Set-SPWOPIZone](set-spwopizone.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[Office Web Apps 서버 배포](deploy-office-web-apps-server.md)  
  

[](deploy-office-web-apps-server.md)

