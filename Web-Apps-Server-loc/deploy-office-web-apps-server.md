---
title Office Web Apps 서버 배포
TOCTitle Office Web Apps 서버 배포
msassetid e4d51dc4-6460-437d-aa8e-0ae4d3aa8cc5
msmtpsurl httpstechnet.microsoft.comko-krlibraryJJ219455(v=office.15)
mscontentKeyID 49643439
ms.date 12182017
mtps_version v=office.15
ms.translationtype HT
---

# Office Web Apps 서버 배포

 

_적용 대상 Office Web Apps Server_

_마지막으로 수정된 항목 2017-10-05_

요약 SharePoint 2013 및 Lync Server 2013에서 사용할 수 있도록 Office Web Apps 서버 온-프레미스를 배포하는 방법을 설명합니다.

대상 IT 전문가

이 문서에서는 비즈니스를 위한 Office Web Apps 서버 설치에 관해 설명합니다. Office 또는 Office Web Apps의 개인용 복사본에 대해 도움이 필요한 경우httpssupport.office.com을 참조하세요.

[Office Web Apps 서버](office-web-apps-server-overview.md) 배포 작업 중에는 일부 필수 구성 소프트웨어가 설치되고 몇 가지 Windows PowerShell 명령이 실행되지만, 전반적인 프로세스는 상당히 간단하게 진행되도록 설계되었습니다. 이 문서에서는 서버 준비 절차를 안내하고 Office Web Apps 서버 팜을 구성하기 위한 Windows PowerShell 명령을 설명합니다.

이 문서의 내용

  - 작업 진행 방식을 확인할 수 있는 비디오 시청

  - 시작하기 전 검토할 리소스

  - Office Web Apps 서버를 실행할 서버 준비

  - Office Web Apps 서버 팜 배포

  - “500 웹 서비스 예외” 또는 “500.21 – 내부 서버 오류” 메시지가 표시되는 경우

## 작업 진행 방식을 확인할 수 있는 비디오 시청

다음 비디오를 시청하여 테스트 환경에서 Office Web Apps 서버를 설정하는 방법을 확인하세요. Office Web Apps 서버를 사용하도록 SharePoint 2013을 구성하는 방법도 확인하도록 합니다.

테스트 환경에서 Office Web Apps 서버 설정

 [!VIDEO httpswww.microsoft.comko-krvideoplayerembed179bf96f-09e1-407a-bb1b-a8e6623eabae]

## 시작하기 전 검토할 리소스

시작하기 전에 다음과 같은 리소스를 확인해야 합니다.

  - 하드웨어 및 소프트웨어 요구 사항에 대한 자세한 내용은 [계획 가이드를 확인](plan-office-web-apps-server.md)하세요.

  - 기본적으로 Office Web Apps 서버에서는 Office 파일을 볼 수만 있고 편집할 수는 없습니다. 파일을 편집하려면 [SharePoint 2013과 함께 사용되는 Office Web Apps 계획](plan-office-web-apps-used-with-sharepoint-2013.md) 및 [SharePoint Server 2013에서 라이선스 구성](httpstechnet.microsoft.comko-krlibraryjj219627(v=office.15))에서 자세한 내용을 확인할 수 있는 편집 라이선스가 있어야 합니다.


 [!NOTE]
 마우스, 바로 가기 키 또는 터치를 통해 모든 Office 2013 제품군에서 작업을 완료할 수 있습니다. Office 제품 및 서비스에서 바로 가기 키와 터치를 사용하는 방법에 대한 자세한 내용은 A href=httpsgo.microsoft.comfwlinkplinkid=249150바로 가기 키A 및 A href=httpsgo.microsoft.comfwlinkplinkid=253163Office 터치 가이드A를 참조하세요.



## Office Web Apps 서버를 실행할 서버 준비

Office Web Apps 서버를 실행할 모든 서버에서 다음 절차를 수행합니다.

그림 Office Web Apps 서버용 서버의 준비 단계

![Office Web Apps 서버용 서버를 준비하기 위한 3가지 기본 단계](imagesJJ219455.af2a4690-4f8b-42c3-aab5-f7066bc0a936(Office.15).gif Office Web Apps 서버용 서버를 준비하기 위한 3가지 기본 단계) 

## 1단계 Office Web Apps 서버의 필수 구성 요소 소프트웨어 설치

Windows Server 2008 R2, Windows Server 2012 및 Windows Server 2012 R2의 필수 구성 요소는 약간 다릅니다. 아래에서 해당하는 프로시저를 선택하여 사용 중인 운영 체제에 알맞은 필수 구성 요소를 설치하세요.

Windows Server 2008 R2

1.  다음 소프트웨어를 설치합니다.
    
      - [Windows Server 2008 R2 서비스 팩 1](httpgo.microsoft.comfwlinkplinkid=252370)
    
      - [.NET Framework 4.5](httpsgo.microsoft.comfwlinkplinkid=256560)
    
      - [Windows PowerShell 3.0](httpsgo.microsoft.comfwlinkplinkid=244693)
    
      - [Windows 7 SP1 및 Windows Server 2008 R2 SP1의 플랫폼 업데이트(KB2670838)](httpsgo.microsoft.comfwlinkplinkid=293629)

2.  Windows PowerShell 프롬프트를 관리자 권한으로 열고 다음 명령을 실행하여 필요한 역할과 서비스를 설치합니다.
    
        Import-Module ServerManager
    
    그런 후 다음 명령을 실행합니다.
    
        Add-WindowsFeature Web-Server,Web-WebServer,Web-Common-Http,Web-Static-Content,Web-App-Dev,Web-Asp-Net,Web-Net-Ext,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,Web-Security,Web-Windows-Auth,Web-Filtering,Web-Stat-Compression,Web-Dyn-Compression,Web-Mgmt-Console,Ink-Handwriting,IH-Ink-Support,NET-Framework,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-Win-CFAC
    
    메시지가 표시되면 서버를 다시 시작합니다.

Windows Server 2012

1.  Windows PowerShell 프롬프트를 관리자 권한으로 열고 다음 명령을 실행하여 필요한 역할과 서비스를 설치합니다.
    
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    
    메시지가 표시되면 서버를 다시 시작합니다.

Windows Server 2012 R2

1.  다음 소프트웨어를 설치합니다.
    
      - [.NET Framework 4.5.2](httpsgo.microsoft.comfwlinkplinkid=510096)

2.  Windows PowerShell 프롬프트를 관리자 권한으로 열고 이 명령을 실행하여 필요한 역할과 서비스를 설치합니다.
    
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    
    메시지가 표시되면 서버를 다시 시작합니다.

## 2단계 Office Web Apps 서버 및 관련 업데이트 설치

Office Web Apps 서버를 실행할 모든 서버에서 다음 단계를 완료합니다.

1.  [VLSC(볼륨 라이선스 서비스 센터)](httpsgo.microsoft.comfwlinkplinkid=256561)에서 Office Web Apps 서버를 다운로드합니다. Office Web Apps 서버를 다운로드하려면 볼륨 라이선스 계약에 따라 Office Professional Plus 2013, Office Standard 2013 또는 Office for Mac 2011의 라이선스가 있어야 합니다. 다운로드 위치는 VLSC 포털에서 해당 Office 제품 아래에 있습니다.

2.  다음 중 하나를 수행합니다.
    
      - Windows Server 2012 또는 Windows Server 2012 R2의 경우 .img 파일을 직접 열고 Setup.exe를 실행합니다.
    
      - Windows Server 2008 R2 SP1의 경우 .img 파일을 탑재하거나 추출할 수 있는 프로그램을 사용한 다음 Setup.exe를 실행합니다.

3.  Microsoft 소프트웨어 사용권 조항 보기 페이지에서 동의함을 선택하고 계속을 클릭합니다.

4.  파일 위치 선택 페이지에서 Office Web Apps 서버 파일을 설치할 폴더(예 CProgram FilesMicrosoft Office Web Apps)를 선택하고 지금 설치를 선택합니다. 지정한 폴더가 없으면 설치 과정에서 자동으로 만들어집니다.
    
    Office Web Apps 서버는 시스템 드라이브에 설치하는 것이 좋습니다.

5.  Office Web Apps 서버의 설치가 완료되면 닫기를 선택합니다.

6.  [Office Web Apps Server SP1](httpsgo.microsoft.comfwlinkplinkid=510097)을 다운로드한 후 설치합니다(Windows Server 2012 및 Windows Server 2008 R2 SP1에는 권장되며 Windows Server 2012 R2에는 필수임).
    

     [!NOTE]
     나중에 Office Web Apps 서버 SP1을 적용할 때 A href=apply-software-updates-to-office-web-apps-server.mdOffice Web Apps 서버에 소프트웨어 업데이트 적용A의 지침을 따르세요.



7.  [Office, Office Server 및 관련 제품의 TechNet 업데이트 센터](httpsgo.microsoft.comfwlinkplinkid=280271)에서 해당 목록을 검토하여 최근의 Office Web Apps 서버 업데이트를 확인합니다.
    

     [!NOTE]
     Office Web Apps Server SP1을 설치하지 않은 경우 A href=httpsgo.microsoft.comfwlinkplinkid=296579KB2810007A을 적용합니다.



## 3단계 Office Web Apps 서버의 언어 팩 설치

Office Web Apps 서버 2013년 언어 팩을 사용하면 SharePoint 2013 문서 라이브러리, Outlook Web Access(첨부 파일 미리 보기) 및 Lync 2013(PowerPoint 브로드캐스트)에서 열리는지에 상관없이 웹 기반 Office 파일을 여러 언어로 볼 수 있습니다. 언어 팩의 작동 방법에 대해 자세히 알아보려면 [Office Web Apps 서버용 언어 팩 계획](plan-office-web-apps-server.md)을 참조하세요.

언어 팩을 설치하려면 다음 단계를 수행합니다.


1.  [Microsoft 다운로드 센터](httpsgo.microsoft.comfwlinkplinkid=263945)에서 Office Web Apps 서버 언어 팩을 다운로드합니다.

2.  WebAppsServerLP_en-us_x64.exe를 실행합니다.

3.  Office Web Apps 서버 2013년 언어 팩 마법사의 Microsoft 소프트웨어 사용권 조항 보기 페이지에서 동의함, 계속을 차례로 선택합니다.

4.  Office Web Apps 서버의 설치가 완료되면 닫기를 선택합니다.


 [!IMPORTANT]
 UL
 LI
 POffice Web Apps 서버 팜을 만들고 나서 언어 팩을 설치하려면 팜에서 서버를 제거하고 팜에 언어 팩을 설치한 다음 서버를 다시 팜에 추가해야 합니다.P
 LI
 P언어 팩이 제대로 작동하려면 팜에 있는 모든 서버에 설치해야 합니다.PLIUL



## Office Web Apps 서버 팜 배포

만들려는 Office Web Apps 서버 팜 종류에 따라 다음의 세 가지 섹션 중 하나에 포함된 절차를 수행합니다.


 [!TIP]
 STRONGNew-OfficeWebAppsFarmSTRONG cmdlet을 실행할 때 Windows PowerShell에서 이 cmdlet을 인식하지 못하면 STRONGOfficeWebAppsSTRONG 모듈을 가져와야 할 수도 있습니다. 다음 명령을 사용하세요.BRCODEImport-Module -Name OfficeWebAppsCODE



## HTTP를 사용하는 단일 서버 Office Web Apps 서버 팜 배포

테스트 또는 내부용으로만 Office Web Apps 서버를 배포하고 Lync Server 2013에 Office Web Apps 서버 기능을 제공할 필요가 없는 경우에는 이 절차가 적합합니다. 여기서 HTTP를 사용하는 단일 서버 Office Web Apps 서버 팜을 설치합니다. 인증서나 부하 분산 장치는 필요하지 않지만 다른 서버 응용 프로그램을 실행하지 않는 전용 실제 서버 또는 가상 컴퓨터 인스턴스는 필요합니다.

Office Web Apps 서버 팜을 사용하여 SharePoint 2013에 Office Web Apps 기능을 제공할 수 있습니다.

그림 Office Web Apps 서버의 배포 단계

![단일 서버 Office Web Apps 서버 팜을 배포하기 위한 3가지 기본 단계](imagesJJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif 단일 서버 Office Web Apps 서버 팜을 배포하기 위한 3가지 기본 단계)

## 1단계 Office Web Apps 서버 팜 만들기

New-OfficeWebAppsFarm 명령을 사용하여 다음 예제와 같이 단일 서버로 구성되는 새로운 Office Web Apps 서버 팜을 만들 수 있습니다.

    New-OfficeWebAppsFarm -InternalURL httpservername -AllowHttp -EditingEnabled

매개 변수

  - –InternalURL 은 httpservername 과 같은 Office Web Apps 서버를 실행하는 서버의 이름입니다.

  - –AllowHttp는 HTTP를 사용하도록 팜을 구성합니다.

  - –EditingEnabled는 SharePoint 2013과 함께 사용할 경우 Office Web Apps에서 편집 기능을 사용할 수 있도록 합니다. 이 매개 변수는 Lync Server 2013에서는 사용되지 않습니다. 이러한 호스트가 편집을 지원하지 않기 때문입니다.

변환 서비스, 프록시 서버, 클립 아트 지원 및 온라인 뷰어를 구성하는 추가 매개 변수는 [New-OfficeWebAppsFarm](new-officewebappsfarm.md)에 설명되어 있습니다.

“500 웹 서비스 예외” 또는 “500.21 – 내부 서버 오류” 메시지가 표시되는 경우

## 2단계 Office Web Apps 서버 팜이 정상적으로 만들어졌는지 확인

팜을 만들고 나면 팜에 대한 세부 정보가 Windows PowerShell 프롬프트에 표시됩니다. Office Web Apps 서버가 제대로 설치 및 구성되었는지 확인하려면 다음 예제에 나와 있는 대로 웹 브라우저를 사용하여 Office Web Apps 서버 검색 URL에 액세스합니다. 검색 URL은 Office Web Apps 서버 팜을 구성할 때 지정한 InternalUrl 매개 변수에 hostingdiscovery가 이어지는 형식으로 구성됩니다.

    httpservernamehostingdiscovery

Office Web Apps 서버가 정상적으로 작동하면 웹 브라우저에 WOPI(웹 응용 프로그램 개방형 플랫폼 인터페이스 프로토콜) 검색 XML 파일이 표시됩니다. 해당 파일의 처음 몇 줄은 아래 예제와 같습니다.

    xml version=1.0 encoding=utf-8  
    - wopi-discovery
    - net-zone name=internal-http
    - app name=Excel favIconUrl=httpservernamex_layoutsimagesFavIcon_Excel.ico checkLicense=true
    action name=view ext=ods default=true urlsrc=httpservernamex_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC&  
    action name=view ext=xls default=true urlsrc=httpservernamex_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC&  
    action name=view ext=xlsb default=true urlsrc=httpservernamex_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC&  
    action name=view ext=xlsm default=true urlsrc=httpservernamex_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC&  

## 3단계 호스트 구성

이제 팜이 HTTP를 통해 호스트에 Office Web Apps 기능을 제공할 준비가 되었습니다. [SharePoint 2013용 Office Web Apps 구성](configure-office-web-apps-for-sharepoint-2013.md)을 방문하여 호스트를 구성하는 방법에 대한 자세한 내용을 알아보세요.

## HTTPS를 사용하는 단일 서버 Office Web Apps 서버 팜 배포

대부분의 프로덕션 환경에서는 보안 기능으로 HTTPS를 사용하는 것이 좋습니다. HTTPS는 Office Web Apps 서버 기능을 Lync Server 2013에 제공하여 브라우저에서 PowerPoint 브로드캐스트를 볼 수 있도록 하려는 경우에도 필요합니다. 다음은 HTTPS를 사용하는 단일 서버 Office Web Apps 서버 팜을 설치하는 방법입니다. [HTTPS를 사용하여 Office Web Apps 서버 통신 보안 유지](plan-office-web-apps-server.md)에 설명된 대로 서버에 인증서를 설치해야 합니다.

이 Office Web Apps 서버 팜은 SharePoint 2013 및 Lync Server 2013에 Office Web Apps 기능을 제공합니다.

그림 Office Web Apps 서버의 배포 단계

![단일 서버 Office Web Apps 서버 팜을 배포하기 위한 3가지 기본 단계](imagesJJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif 단일 서버 Office Web Apps 서버 팜을 배포하기 위한 3가지 기본 단계)

## 1단계 Office Web Apps 서버 팜 만들기

New-OfficeWebAppsFarm 명령을 사용하여 다음 예제와 같이 단일 서버로 구성되는 새로운 Office Web Apps 서버 팜을 만들 수 있습니다.

    New-OfficeWebAppsFarm -InternalUrl httpsserver.contoso.com -ExternalUrl httpswacweb01.contoso.com -CertificateName OfficeWebApps Certificate -EditingEnabled

매개 변수

  - –InternalURL 은 httpservername.contoso.com 과 같은 Office Web Apps 서버 실행 서버의 FQDN(정규화된 도메인 이름)입니다.

  - –ExternalURL은 인터넷에서 액세스할 수 있는 FQDN입니다.

  - –CertificateName은 인증서의 이름입니다.

  - –EditingEnabled는 선택 사항이며, SharePoint 2013과 함께 사용할 경우 Office Web Apps에서 편집 기능을 사용할 수 있도록 합니다. 이 매개 변수는 Lync Server 2013에서는 사용되지 않습니다. 이러한 호스트가 편집을 지원하지 않기 때문입니다.

변환 서비스, 프록시 서버, 클립 아트 지원 및 온라인 뷰어를 구성하는 추가 매개 변수는 [New-OfficeWebAppsFarm](new-officewebappsfarm.md)에 설명되어 있습니다.

“500 웹 서비스 예외” 또는 “500.21 – 내부 서버 오류” 메시지가 표시되는 경우

## 2단계 Office Web Apps 서버 팜이 정상적으로 만들어졌는지 확인

팜을 만들고 나면 팜에 대한 세부 정보가 Windows PowerShell 프롬프트에 표시됩니다. Office Web Apps 서버가 제대로 설치 및 구성되었는지 확인하려면 다음 예제에 나와 있는 대로 웹 브라우저를 사용하여 Office Web Apps 서버 검색 URL에 액세스합니다. 검색 URL은 Office Web Apps 서버 팜을 구성할 때 지정한 InternalUrl 매개 변수에 hostingdiscovery가 이어지는 형식으로 구성됩니다. 예를 들면 다음과 같습니다.

    httpsserver.contoso.comhostingdiscovery

Office Web Apps 서버가 정상적으로 작동하면 웹 브라우저에 WOPI(웹 응용 프로그램 개방형 플랫폼 인터페이스 프로토콜) 검색 XML 파일이 표시됩니다. 해당 파일의 처음 몇 줄은 아래 예제와 같습니다.

``` 
xml version=1.0 encoding=UTF-8
wopi-discoverynet-zone 
name=internal-httpsapp name=Excel checkLicense=true 
favIconUrl=httpswac.contoso.comx_layoutsimagesFavIcon_Excel.icoaction 
name=view 
urlsrc=httpswac.contoso.comx_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC& 
default=true ext=odsaction name=view 
urlsrc=httpswac.contoso.comx_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC& 
default=true ext=xlsaction name=view
 
```


 [!NOTE]
 웹 브라우저의 보안 설정에 따라서는 검색 XML 파일의 콘텐츠가 표시되기 전에 STRONG모든 콘텐츠 표시STRONG를 선택하라는 메시지가 표시될 수도 있습니다.



## 3단계 호스트 구성

이제 팜이 HTTPS를 통해 호스트에 Office Web Apps 기능을 제공할 준비가 되었습니다. 호스트를 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

  - [SharePoint 2013용 Office Web Apps 구성](configure-office-web-apps-for-sharepoint-2013.md)

  - [Office Web Apps Server 및 Lync Server 2013 배포](httpsgo.microsoft.comfwlinkplinkid=256902)

## HTTPS를 사용하는 부하 분산된 다중 서버 Office Web Apps 서버 팜 배포

Office Web Apps 서버 팜에 트래픽이 많이 발생할 것으로 예상되고 인터넷과 내부 네트워크를 통해 사용할 수 있도록 하려면 이와 같은 유형의 토폴로지를 사용하는 것이 적절합니다. 이 섹션에는 부하 분산 장치 및 HTTPS를 사용하는 다중 서버 Office Web Apps 서버 팜을 설치하는 방법이 나와 있습니다. 관심이 있는 경우 [이 토폴로지에 대한 자세한 정보](plan-office-web-apps-server.md)를 읽어보세요.

시작하기 전에 [Office Web Apps Server의 부하 분산 장치 요구 사항](plan-office-web-apps-server.md)에 설명된 대로 부하 분산 장치가 구성되어 있는지 확인합니다. 또한 [HTTPS를 사용하여 Office Web Apps Server 통신 보안 유지](plan-office-web-apps-server.md)에 설명된 대로 부하 분산 장치에 인증서를 설치해야 합니다. 이 Office Web Apps 서버 팜은 SharePoint 2013 및 Lync Server 2013에 Office Web Apps 기능을 제공합니다.

그림 Office Web Apps 서버의 배포 단계

![다중 서버 Office Web Apps 서버 팜을 배포하기 위한 4가지 기본 단계](imagesJJ219455.4c4b31cb-961b-4efd-b755-a18bdcb5c191(Office.15).gif 다중 서버 Office Web Apps 서버 팜을 배포하기 위한 4가지 기본 단계)

## 1단계 첫 번째 서버에서 Office Web Apps 서버 팜 만들기

New-OfficeWebAppsFarm 명령을 사용하여 다음 예제와 같이 첫 번째 서버에 새로운 Office Web Apps 서버 팜을 만들 수 있습니다.

    New-OfficeWebAppsFarm -InternalUrl httpsserver.contoso.com -ExternalUrl httpswacweb01.contoso.com -SSLOffloaded -EditingEnabled

매개 변수

  - –InternalURL 은 httpservername.contoso.com 과 같은 Office Web Apps 서버 실행 서버의 FQDN(정규화된 도메인 이름)입니다.

  - –ExternalURL 은 인터넷에서 액세스할 수 있는 FQDN 이름입니다.

  - -SSLOffloaded 는 부하 분산 장치로 SSL 종료 장치를 오프로드할 수 있도록 합니다.

  - –EditingEnabled 는 선택 사항이며, SharePoint 2013과 함께 사용할 경우 Office Web Apps에서 편집 기능을 사용할 수 있도록 합니다. 이 매개 변수는 Lync Server 2013에서는 사용되지 않습니다. 이러한 호스트가 편집을 지원하지 않기 때문입니다.

변환 서비스, 프록시 서버, 클립 아트 지원 및 온라인 뷰어를 구성하는 기타 매개 변수는 [New-OfficeWebAppsFarm](new-officewebappsfarm.md)에 설명되어 있습니다.

“500 웹 서비스 예외” 또는 “500.21 – 내부 서버 오류” 메시지가 표시되는 경우

## 2단계 팜에 서버 더 추가

첫 번째 서버에서 Office Web Apps 서버를 실행한 후 Office Web Apps 서버 팜에 추가할 각 서버에서 New-OfficeWebAppsMachine 명령을 실행합니다. –MachineToJoin 매개 변수는 Office Web Apps 서버 팜에 이미 있는 서버의 컴퓨터 이름을 사용합니다. 예를 들어 server1.contoso.com이 팜에 이미 있으면 다음을 사용합니다.

    New-OfficeWebAppsMachine -MachineToJoin server1.contoso.com

이러한 매개 변수에 대한 자세한 내용은 [New-OfficeWebAppsMachine](new-officewebappsmachine.md)에서 확인할 수 있습니다.

## 3단계 Office Web Apps 서버 팜이 정상적으로 만들어졌는지 확인

팜을 만들고 나면 팜에 대한 세부 정보가 Windows PowerShell 프롬프트에 표시됩니다. Office Web Apps 서버가 제대로 설치 및 구성되었는지 확인하려면 다음 예제에 나와 있는 것처럼 웹 브라우저를 사용하여 Office Web Apps 서버 검색 URL에 액세스합니다. 검색 URL은 Office Web Apps 서버 팜을 구성할 때 지정한 InternalUrl 매개 변수에 hostingdiscovery 가 이어지는 형식으로 구성됩니다. 예를 들면 다음과 같습니다.

    httpsserver.contoso.comhostingdiscovery

Office Web Apps 서버가 정상적으로 작동하면 웹 브라우저에 WOPI(웹 응용 프로그램 개방형 플랫폼 인터페이스 프로토콜) 검색 XML 파일이 표시됩니다. 해당 파일의 처음 몇 줄은 아래 예제와 같습니다.

    xml version=1.0 encoding=UTF-8
    wopi-discoverynet-zone name=internal-httpsapp name=Excel checkLicense=true favIconUrl=httpsofficewebapps.contoso.comx_layoutsimagesFavIcon_Excel.icoaction name=view urlsrc=httpsofficewebapps.contoso.comx_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC& default=true ext=odsaction name=view urlsrc=httpsofficewebapps.contoso.comx_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC& default=true ext=xlsaction name=view urlsrc=httpsofficewebapps.contoso.comx_layoutsxlviewerinternal.aspxui=UI_LLCC&rs=DC_LLCC& default=true ext=xlsb 


 [!NOTE]
 웹 브라우저의 보안 설정에 따라서는 검색 XML 파일의 콘텐츠가 표시되기 전에 STRONG모든 콘텐츠 표시STRONG를 선택하라는 메시지가 표시될 수도 있습니다.



## 4단계 호스트 구성

이제 팜이 HTTPS를 통해 호스트에 Office Web Apps 기능을 제공할 준비가 되었습니다. 호스트를 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

  - [SharePoint 2013용 Office Web Apps 구성](configure-office-web-apps-for-sharepoint-2013.md)

  - [Office Web Apps Server 및 Lync Server 2013 배포](httpsgo.microsoft.comfwlinkplinkid=256902)

## “500 웹 서비스 예외” 또는 “500.21 – 내부 서버 오류” 메시지가 표시되는 경우

.NET Framework 3.5 기능을 설치했다가 제거한 경우 OfficeWebApps cmdlet을 실행하면 500 웹 서비스 예외 또는 500.21 - 내부 서버 오류 메시지가 표시될 수도 있습니다. 이 문제를 해결하려면 관리자 권한 명령 프롬프트에서 다음 예제 명령을 실행하여 Office Web Apps 서버가 제대로 작동하지 않도록 하는 설정을 정리합니다.

Windows Server 2008 R2의 경우

    %systemroot%Microsoft.NETFramework64v4.0.30319aspnet_regiis.exe -iru

    iisreset restart noforce

Windows Server 2012 또는 Windows Server 2012 R2의 경우

    dism online enable-feature featurenameIIS-ASPNET45

## 참고 항목


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[Office Web Apps 서버 계획](plan-office-web-apps-server.md)  
[SharePoint 2013용 Office Web Apps 구성](configure-office-web-apps-for-sharepoint-2013.md)  


[Office Web Apps Server 및 Lync Server 2013 배포](httpsgo.microsoft.comfwlinkplinkid=256902)  
  

[](configure-office-web-apps-for-sharepoint-2013.md)

