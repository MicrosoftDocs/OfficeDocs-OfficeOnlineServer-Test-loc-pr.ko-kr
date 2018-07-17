---
title: '비디오: SharePoint 2013용 Office Web Apps 구성'
TOCTitle: '비디오: SharePoint 2013용 Office Web Apps 구성'
ms:assetid: 0c02633f-3839-448b-ae83-24f24c254179
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Dn455088(v=office.15)
ms:contentKeyID: 59152176
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# 비디오: SharePoint 2013용 Office Web Apps 구성

 

_<strong>적용 대상:</strong>Office Web Apps, Office Web Apps Server, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>마지막으로 수정된 항목:</strong>2016-12-16_

**요약:** SharePoint 2013에서 작업할 Office Web Apps 서버 팜을 구성하기 위한 9가지 기본 단계를 안내합니다.

SharePoint 2013에 맞게 Office Web Apps를 구성하는 과정은 아주 간단합니다. 이 비디오는 테스트 환경에서 Office Web Apps 서버를 사용하도록 Office Web Apps 서버를 설정하고 SharePoint 2013을 구성하는 방법을 보여줍니다.


**"SharePoint 2013용 Office Web Apps 구성" 비디오를 시청하세요.**

> [!VIDEO https://www.microsoft.com/ko-kr/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

이 비디오에서는 Office Web Apps 서버를 실행하는 서버와 SharePoint 2013을 실행하는 서버에서 수행되는 절차를 설명합니다. 이러한 서버는 [Office Web Apps 서버용 소프트웨어, 하드웨어 및 구성 요구 사항](plan-office-web-apps-server.md)에 설명된 바와 같이 별도의 서버여야 합니다.

**Office Web Apps 서버 실행 서버의 경우 비디오를 통해 다음 방법을 확인할 수 있습니다.**

1\. Windows PowerShell 명령 프롬프트를 열고 Office Web Apps 서버에 필요한 역할과 서비스를 설치합니다. [Office Web Apps 서버를 실행하도록 서버 준비](deploy-office-web-apps-server.md)를 참조하세요. 필요한 역할과 서비스가 없으면 Office Web Apps 서버가 설치되지 않기 때문에 이 작업이 필요합니다.  
2\. [VLSC(볼륨 라이선스 서비스 센터)](http://go.microsoft.com/fwlink/p/?linkid=256561)에서 Office Web Apps 서버 소프트웨어를 설치합니다.Office Web Apps 서버를 다운로드하려면 볼륨 라이선스 계약에 따라 Office Professional Plus 2013, Office Standard 2013 또는 Office for Mac 2011에 대한 라이선스가 있어야 합니다. 다운로드 위치는 VLSC 포털에서 해당 Office 제품 아래에 있습니다.  
3\. [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)을 사용하여 Office Web Apps 서버 팜을 만듭니다.  
4\. 브라우저 창을 열고 http://*ServerName*/hosting/discovery로 이동하여 Office Web Apps 서버 팜이 만들어졌는지 확인합니다.

**SharePoint 2013 실행 서버의 경우 비디오를 통해 다음 방법을 확인할 수 있습니다.**

5\. SharePoint 2013 관리 셸을 엽니다.  
6\. [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps)을 사용하여 Office Web Apps 서버와 SharePoint 2013 사이에 바인딩을 만듭니다. 이렇게 하면 SharePoint 2013 실행 서버와 Office Web Apps 서버 실행 서버 사이에 통신이 설정됩니다.  
7\. [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps)을 사용하여 SharePoint 2013의 WOPI 영역을 확인합니다. 이 단계에서는 두 서버가 다른 WOPI 영역을 사용하고 있다는 사실이 강조 표시됩니다. 즉 SharePoint 2013은 internal-https를 사용하고, Office Web Apps 서버는 internal-http를 사용합니다. 올바르게 작동하려면 해당 영역이 Office Web Apps와 일치해야 합니다.  
8\. WOPI 영역을 internet-http로 변경하려면 [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps)을 사용하여 SharePoint 2013에 대한 WOPI 영역을 변경합니다.  
9\. SharePoint 2013 문서 라이브러리에서 Office 문서를 열어 Office Web Apps가 작동하고 있는지 확인합니다.

이러한 각 단계에 대한 자세한 내용은 [Office Web Apps 서버 배포](deploy-office-web-apps-server.md) 및 [SharePoint 2013용 Office Web Apps 구성](configure-office-web-apps-for-sharepoint-2013.md) 문서에서 다음 섹션을 참조하세요.

  - [Office Web Apps 서버를 실행하도록 서버 준비](deploy-office-web-apps-server.md)

  - [테스트 환경에서 단일 서버 Office Web Apps 서버 팜 배포](deploy-office-web-apps-server.md)

  - [Office Web Apps 서버를 사용하도록 SharePoint 2013 구성 준비](configure-office-web-apps-for-sharepoint-2013.md)

  - [HTTP를 사용하는 테스트 환경에서 Office Web Apps 서버를 사용하도록 SharePoint 2013 구성](configure-office-web-apps-for-sharepoint-2013.md)

## 참고 항목


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 사용되는 Office Web Apps 계획](plan-office-web-apps-used-with-sharepoint-2013.md)  
[Office Web Apps가 SharePoint 2013에서 온-프레미스로 작동하는 방식](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

