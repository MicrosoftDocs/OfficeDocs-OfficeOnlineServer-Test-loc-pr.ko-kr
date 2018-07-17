---
title: SharePoint 2013과 함께 사용되는 Office Web Apps 계획
TOCTitle: Office Web Apps 계획
ms:assetid: 3bd0a617-5f12-4a7e-bb75-b15c86c7e504
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Ff431682(v=office.15)
ms:contentKeyID: 49643368
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# SharePoint 2013과 함께 사용되는 Office Web Apps 계획

 

_<strong>적용 대상:</strong>Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>마지막으로 수정된 항목:</strong>2016-12-16_

**요약:** SharePoint 2013 온-프레미스와 함께 사용하는 경우의 Office Web Apps에 대한 계획 지침을 검토합니다.

**대상:** IT 전문가

Office Web Apps 온-프레미스를 SharePoint 2013과 함께 사용하는 방법을 계획하려면 Office Web Apps를 사용하여 Office 파일을 보고 편집하기 위한 브라우저 지원, SharePoint 인증 요구 사항 및 라이선스 고려 사항을 검토해야 합니다. 그런 후에 사용자가 SharePoint 2013 문서 라이브러리에서 Office 파일을 열 때 SharePoint 2013에서 사용하도록 할 항목(웹 브라우저 또는 클라이언트 응용 프로그램)을 결정할 수 있습니다.


> [!IMPORTANT]
> 이 문서는 <A href="content-roadmap-for-office-web-apps-server.md">Office Web Apps 서버의 콘텐츠 로드맵</A>의 일부입니다. 이 로드맵을 Office Web Apps 서버 배포 및 관리를 위한 문서, 다운로드 및 비디오의 시작 지점으로 활용하세요.<BR><STRONG>데스크톱 또는 모바일 장치에서 Office Web Apps 도움말을 찾으십니까?</STRONG> <A href="http://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</A>에서 "Office Web Apps"로 검색하면 필요한 정보를 확인하실 수 있습니다.



이 문서의 내용

  - Office Web Apps 계획 정보

  - Office Web Apps에 대한 브라우저 지원

  - Office Web Apps에 대한 SharePoint 인증 요구 사항

  - Office 파일 편집을 위해 Office Web Apps 라이선스 적용

  - SharePoint 2010과 함께 Office Web Apps를 배포한 고객의 고려 사항

  - SharePoint 2013 문서 라이브러리에서 여는 문서의 기본 열기 동작

## Office Web Apps 계획 정보

이 문서의 지침은 조직에서 온-프레미스로 Office Web Apps 서버를 배포할 때 수행하는 전체 계획에 포함됩니다. 예를 들어 하드웨어/소프트웨어/가상화 요구 사항, 팜 크기 지정/토폴로지, 보안 등은 모두 Office Web Apps 서버 계획에 포함됩니다. 이러한 사항을 결정한 후에는 SharePoint 2013 관련 Office Web Apps 기능을 구성할 방법을 계획할 수 있습니다. Office Web Apps 서버에 대해 잘 모르거나 해당 요구 사항 및 계획 지침을 검토하지 않은 경우에는 [Office Web Apps 서버 개요](office-web-apps-server-overview.md) 및 [Office Web Apps 서버 계획](plan-office-web-apps-server.md)을 참조하십시오.

## Office Web Apps에 대한 브라우저 지원

Office Web Apps에 대한 브라우저 지원은 SharePoint 2013에서와 동일합니다. 자세한 내용은 [SharePoint 2013의 브라우저 지원 계획](https://technet.microsoft.com/ko-kr/library/cc263526\(v=office.15\)) 문서를 참조하십시오.

## Office Web Apps에 대한 SharePoint 인증 요구 사항

Office Web Apps는 클레임 기반 인증을 사용하는 SharePoint 2013 웹 응용 프로그램에서만 사용할 수 있습니다. Office Web Apps 렌더링 및 편집 기능은 클래식 모드 인증을 사용하는 SharePoint 2013 웹 응용 프로그램에서 작동하지 않습니다. 클래식 모드 인증을 사용하는 SharePoint 2010 웹 응용 프로그램을 SharePoint 2013으로 마이그레이션하는 경우에는 Office Web Apps에서 작동하도록 해당 응용 프로그램을 클레임 기반 인증으로 마이그레이션해야 합니다. 자세한 내용은 [SharePoint 2013에서 클래식 모드에서 클레임 기반 인증으로 마이그레이션](https://technet.microsoft.com/ko-kr/library/gg251985\(v=office.15\))을 참조하십시오.

## Office 파일 편집을 위해 Office Web Apps 라이선스 적용

볼륨 라이선스 프로그램을 통해 Office 2013 라이선스를 받은 기업 고객의 경우 SharePoint 2013 온-프레미스에 대해 Office Web Apps 편집을 사용하도록 설정할 수 있습니다. 따라서 사용자는 집이나 Office 클라이언트가 설치되지 않았을 수 있는 다른 위치에서 Office 편집 기능을 사용할 수 있습니다.

사용 중인 라이선스에 대한 정확한 정보는 Office Web Apps 서버 설치 시 표시되는 Microsoft 소프트웨어 사용권 조항을 참조하십시오. SharePoint 2013에서 라이선스가 작동하는 방식에 대한 자세한 내용은 [SharePoint Server 2013에서 라이선스 구성](https://technet.microsoft.com/ko-kr/library/jj219627\(v=office.15\))을 참조하십시오.

## 데이터베이스 연결 방법을 사용하여 SharePoint 2010에서 업그레이드하는 고객의 고려 사항

Office Web Apps를 SharePoint 2010과 함께 설치한 경우 SharePoint 2013으로 업그레이드하고 나면 Office Web Apps를 사용할 수 없습니다. 따라서 콘텐츠 데이터베이스를 업그레이드한 후에 Office Web Apps 서버를 배포한 다음 SharePoint 2013을 연결해야 합니다. Office Web Apps 서버는 SharePoint 2013에서 2010 및 2013 사이트 모음 모드를 모두 지원하므로 사이트 모음을 업그레이드할 때까지 기다리지 않아도 됩니다. 데이터베이스 연결 방법에 대한 자세한 내용은 [SharePoint 2013으로의 업그레이드 프로세스 개요](https://technet.microsoft.com/ko-kr/library/cc262483\(v=office.15\))를 참조하십시오.

## SharePoint 2013 문서 라이브러리에서 여는 문서의 기본 열기 동작

Word, PowerPoint, Excel 및 OneNote 파일이 클라이언트 응용 프로그램(설치되어 있는 경우)에서 열리는지 아니면 브라우저에서 열리는지를 구성할 수 있습니다. 기본적으로 SharePoint 2013이 Office Web Apps 서버를 사용하도록 구성하고 나면 Office 파일은 브라우저에서 열립니다. 다음 두 가지 방법으로 이 기본 동작을 변경하여 파일이 클라이언트 응용 프로그램에서 바로 열리도록 할 수 있습니다.

  - **SharePoint 2013 팜의 경우** [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps) 및 [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps)Windows PowerShell cmdlet을 사용하여 SharePoint 2013 팜에 대해 파일 형식별로 기본 열기 동작을 조정할 수 있습니다.

  - **사이트 모음 또는 문서 라이브러리의 경우** 사이트 모음 관리자 및 사용자는 Office 파일이 클라이언트 응용 프로그램(설치되어 있는 경우)에서 열리도록 할지를 지정할 수 있습니다. 사용자는 문서 라이브러리 속성에서 이 설정을 변경할 수 있으며 사이트 모음 관리자는 사이트 모음 관리에서 또는 Install-SPFeature cmdlet을 사용하여 OpenInClient 기능을 설치함으로써 이 설정을 변경할 수 있습니다. 자세한 내용은 [Install-SPFeature](https://technet.microsoft.com/ko-kr/library/ff607825\(v=office.15\))를 참조하십시오.

## 참고 항목


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[Office Web Apps가 SharePoint 2013에서 온-프레미스로 작동하는 방식](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  


[HTTP를 사용하는 테스트 환경에서 Office Web Apps 서버 미리 보기를 사용하도록 SharePoint 2013 미리 보기 구성](configure-office-web-apps-for-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

