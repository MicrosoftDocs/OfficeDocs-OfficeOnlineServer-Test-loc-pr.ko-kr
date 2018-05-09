---
title: Office Web Apps가 SharePoint 2013에서 온-프레미스로 작동하는 방식
TOCTitle: SharePoint 2013의 Office Web Apps 온-프레미스
ms:assetid: 8480064e-14a4-4b46-ad6b-0c836b192af2
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Ff431685(v=office.15)
ms:contentKeyID: 49643381
ms.date: 02/07/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Office Web Apps가 SharePoint 2013에서 온-프레미스로 작동하는 방식

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2016-12-16_

**요약:** Office Web Apps, Office Web Apps 서버에 대한 내용과 이러한 제품이 SharePoint 2013과 함께 온-프레미스에서 작동하는 방법에 대해 설명합니다.

**대상:** IT 전문가

Office Web Apps 서버를 SharePoint Server 2013과 함께 사용하는 경우 업데이트된 버전의 Word Web App, Excel Web App, PowerPoint Web App 및 OneNote Web App을 제공합니다. 사용자는 컴퓨터와 Windows Phone, iPhone, iPad, Windows 8 태블릿, Android 장치 등의 많은 모바일 장치에서 지원되는 웹 브라우저를 사용하여 SharePoint 라이브러리의 Office 문서를 볼 수 있으며, 경우에 따라 편집할 수도 있습니다.


**그림: 각 장치 유형에서 제공되는 Office Web Apps의 보기 및 편집 기능**

![각 장치 유형에서 제공되는 Office Web Apps의 보기 및 편집 기능이 요약된 그래픽. 터치 스크린에 최적화된 기능을 강조 표시합니다.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "각 장치 유형에서 제공되는 Office Web Apps의 보기 및 편집 기능이 요약된 그래픽. 터치 스크린에 최적화된 기능을 강조 표시합니다.")

## 현재 독립 실행형 서버로 설치되는 Office Web Apps 서버

Office Web Apps는 SharePoint 2013을 실행하는 것과 같은 서버에 설치하지 않습니다. 대신 Office Web Apps 서버를 실행하는 하나 이상의 실제 서버 또는 가상 서버를 배포한 다음, Office Web Apps 서버 팜을 사용하여 SharePoint 라이브러리에서 Office 파일을 만들거나 여는 사용자에게 Office Web Apps 기능을 제공하도록 SharePoint 2013 팜을 구성합니다. 자세한 내용은 [Office Web Apps 서버 개요](office-web-apps-server-overview.md)를 참조하세요.

## SharePoint 2013에서 사용할 때 Office Web Apps의 사용을 허가하기 위한 옵션

Office Web Apps 라이선스에서는 두 가지 옵션이 제공됩니다.

  - **보기만**. 기본적으로 Office Web Apps는 보기 전용입니다. 보기 전용 기능은 무료로 제공됩니다.

  - **편집 및 보기**. Office Web Apps의 편집 기능을 SharePoint 2013에서 사용하려면 편집 라이선스를 구입해야 합니다. Office Web Apps 서버 팜을 만들 때 편집 기능을 사용하도록 설정합니다.

조직에서 볼륨 라이선스 프로그램을 통해 Office 2013 라이선스를 받은 경우 SharePoint 2013 온-프레미스에서 Office Web Apps 편집 기능을 사용하도록 설정할 수 있습니다. 이에 따라 사용자는 집이나 Office 클라이언트가 설치되어 있지 않을 수 있는 다른 위치에서 Office 편집 기능을 사용할 수 있습니다. Office Web Apps용 편집 라이선스를 별도로 구입할 수는 없습니다.

사용 중인 라이선스에 대한 정확한 정보는 Office Web Apps 서버 설치 시 표시되는 Microsoft 소프트웨어 사용권 조항을 참조하십시오.

SharePoint 2013에서는 Office Web Apps에서 작동하는 새로운 라이선스 적용 기능을 제공합니다. SharePoint 라이선스를 사용하도록 설정한 다음 Office Web Apps 편집을 사용하도록 설정하면 해당하는 라이선스가 있는 사용자만 실제로 브라우저에서 Office 파일을 편집할 수 있습니다. 사용자에게 적용된 Office Web Apps 편집 라이선스가 없으면 보기 기능만 지원됩니다.

라이선스가 SharePoint 2013에서 작동하는 방법에 대한 자세한 내용은 [SharePoint Server 2013에서 라이선스 구성](https://technet.microsoft.com/ko-kr/library/jj219627\(v=office.15\))을 참조하세요. 편집 기능을 사용하도록 설정하는 EditingEnabled 매개 변수에 대한 설명은 [New-OfficeWebAppsFarm](new-officewebappsfarm.md) 및 [Set-OfficeWebAppsFarm](set-officewebappsfarm.md)에 나와 있습니다.

SharePoint 2013의 링크로 공유 기능을 통해 전송되는 파일은 편집 라이선스가 없고 Office Web Apps 서버 팜에 대해 편집이 사용하지 않도록 설정되어 있어도 Office Web Apps에서 편집할 수 있습니다.

## Office 모바일 뷰어를 사용하여 SharePoint 사이트의 파일에 액세스

Office Web Apps 서버에서는 Office 모바일 뷰어를 제공하여 SharePoint Server 사이트에 액세스하는 모바일 사용자가 Office Web Apps를 사용할 수 있도록 합니다. Office 모바일 뷰어는 기본적으로 사용하도록 설정되지만 SharePoint Server 사이트 관리자가 사용하지 않도록 설정할 수도 있습니다. 이 뷰어를 사용하도록 설정하면 각자의 모바일 장치 브라우저를 사용하여 SharePoint Server 사이트로 이동한 후 SharePoint Server 라이브러리에서 열려는 문서를 누르면 해당 문서가 모바일 브라우저에서 열립니다.

[SharePoint 2013의 새로운 모바일 장치 기능](https://technet.microsoft.com/ko-kr/library/fp161352\(v=office.15\)) 및 [Overview of mobile devices and SharePoint Server 2013](https://technet.microsoft.com/ko-kr/library/fp161351\(v=office.15\))에서 모바일 장치의 SharePoint 라이브러리에 대해 자세히 알아볼 수 있습니다. 사용자는 [Android, iPhone 또는 Windows Phone에서 Office Web Apps 사용](http://go.microsoft.com/fwlink/p/?linkid=271045)을 통해 모바일 장치에서 Office 모바일 뷰어를 사용하는 방법에 대해 자세히 알아볼 수 있습니다. SharePoint 2013에서 Office 모바일 뷰어를 사용하지 않도록 결정한 경우 [Remove-SPWOPIBinding](remove-spwopibinding.md) cmdlet을 사용하세요.

## SharePoint의 Excel Services와 Excel Web App 간 차이점

SharePoint의 Excel Services 및 Excel Web App은 매우 비슷하지만 같지는 않습니다. Excel Services는 SharePoint Server 2013 Enterprise 버전에서만 사용할 수 있고, Excel Web App은 SharePoint Server 2013 및 SharePoint Foundation 2013에서 사용할 수 있습니다. 두 응용 프로그램을 사용하여 브라우저 창에서 통합 문서를 볼 수 있을 뿐만 아니라 데이터와 상호 작용하고 데이터를 탐색할 수 있습니다.

그러나 SharePoint의 Excel Services 및 Excel Web App 간에는 특정한 차이점이 있습니다. 예를 들어 Excel Services는 외부 데이터 연결, 데이터 모델 및 데이터 모델을 사용하는 항목(예: 피벗 차트 보고서, 피벗 테이블 보고서, 시간 표시줄 컨트롤) 간의 상호 작용 기능을 지원합니다. 또한 Excel Services에서는 Excel Web App보다 많은 비즈니스 인텔리전스 기능을 제공하지만, Excel Services에서는 브라우저 창에서 통합 문서를 만들거나 편집할 수 없습니다.

Excel Web App 및 Excel Services 간의 차이점에 대한 자세한 내용은 [SharePoint Server 2013의 Excel Services 개요](https://technet.microsoft.com/ko-kr/library/ee424405\(v=office.15\)) 및 [SharePoint의 Excel Services와 Excel Web App 비교](http://go.microsoft.com/fwlink/p/?linkid=255460)를 참조하세요.

조직에서 Excel Web App이 아닌 Excel Services를 사용하여 브라우저에서 통합 문서를 보도록 하는 경우에는 Windows PowerShell **New-SPWOPISuppressionSettings** cmdlet을 사용하여 Excel 통합 문서에 대해 Excel Web App을 해제할 수 있습니다. 자세한 내용은 [New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)을 참조하십시오.

## 참고 항목


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 사용되는 Office Web Apps 계획](plan-office-web-apps-used-with-sharepoint-2013.md)  
  

[](plan-office-web-apps-used-with-sharepoint-2013.md)

