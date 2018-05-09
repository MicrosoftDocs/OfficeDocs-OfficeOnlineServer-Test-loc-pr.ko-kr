---
title: Office Web Apps 서버 개요
TOCTitle: '개요: Office Web Apps 서버'
ms:assetid: 4b199a88-387f-4121-820d-7af580e2a3e8
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219437(v=office.15)
ms:contentKeyID: 49643371
ms.date: 02/08/2018
mtps_version: v=office.15
ms.translationtype: MT
---

# Office Web Apps 서버 개요

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2017-05-26_

**요약:** Office Web Apps 서버 및 이 제품에서 지원되는 호스트에 대해 브라우저 기반 Office 기능을 제공하는 방법을 설명합니다.

**대상:** IT 전문가

Office Web Apps 서버 는 브라우저 기반 버전의 Word, PowerPoint, Excel 및 OneNote 이 제공 하는 새 Office 서버 제품입니다. 단일 Office Web Apps 서버 팜에서 Office 파일 SharePoint 2013, Lync Server 2013, 폴더, 공유 폴더 및 웹사이트를 통해 액세스 하는 사용자를 지원할 수 있습니다. 새로운 독립 실행형 배포 모델 Office Web Apps 서버 팜에 배포 되는 다른 Office 서버 제품에 관계 없이 조직에서 업데이트를 관리할 수 있다는 것을 의미 합니다.


> [!IMPORTANT]
> 이 문서는 <A href="content-roadmap-for-office-web-apps-server.md">Office Web Apps 서버의 콘텐츠 로드맵</A>의 일부입니다. 이 로드맵을 Office Web Apps 서버 배포 및 관리를 위한 문서, 다운로드 및 비디오의 시작 지점으로 활용하세요.<BR><STRONG>데스크톱 또는 모바일 장치에서 Office Web Apps 도움말을 찾으십니까?</STRONG> <A href="https://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</A>에서 "Office Web Apps"로 검색하면 필요한 정보를 확인하실 수 있습니다.



이 문서의 내용

  - Office Web Apps 서버 정보

  - SharePoint 2013에서 Office Web Apps 서버를 사용하여 Office 문서를 보고 편집하는 방법

  - Lync Server 2013에서 Office Web Apps 서버를 사용하여 PowerPoint 브로드캐스트를 보는 방법

  - Office Web Apps 서버를 통해 온라인 뷰어를 사용하여 공유 폴더와 웹 사이트에서 Office 파일을 볼 수 있는 방법

## Office Web Apps 서버 정보

Office Web Apps 서버 는 브라우저 기반 파일 보기 및 편집 Office 파일에 대 한 서비스를 제공 하는 Office 서버 제품입니다. Office Web Apps 서버 제품 및 WOPI, 웹 응용 프로그램 열기 플랫폼 인터페이스 프로토콜을 지 원하는 서비스를 사용 하 여 사용할 수 있습니다. 호스트 라고 하는 이러한 제품에는 SharePoint 2013 및 Lync Server 2013 포함 됩니다. Office Web Apps 서버 팜에 여러 온-프레미스 호스트에 Office 서비스를 제공할 수 및 조직의 증가 필요에 따라 여러 서버에 서버에서 팜 확장할 수 있습니다. Office Web Apps 서버 필요 없는 다른 서버 응용 프로그램을 실행 하는 전용된 서버, 하지만 대신 Office Web Apps 서버 인스턴스 가상 컴퓨터에 설치할 수 있습니다.

배포 하 고 해당 응용 프로그램은 독립 실행형 제품 했으므로 Office Web Apps 조직 내에서 관리 하는 것이 쉽습니다. SharePoint 2013 를 배포 하는 경우 예 더이상 해야 SharePoint Server 2010 와 긴밀 하 게 통합 된 이전 버전에는 Office Web Apps를 지원 하기 위해 SharePoint 인프라를 최적화 합니다. 또한 업데이트를 적용 하면 Office Web Apps 서버 팜에 별도로 하 고 다른 빈도로 SharePoint 또는 Lync 서버를 업데이트 하는 보다 합니다. 또한, 독립 실행형 Office Web Apps 서버 팜에 있는 사용자 수 보거나 저장 된 외부 SharePoint Server, 공유 폴더 또는 기타 웹사이트에서의 연결과 같이 수 있는 Office 파일을 편집 하는 의미 합니다. 이 기능은 온라인 뷰어 라고 하는 기능에 의해 제공 됩니다.

다음 그림에는 Office Web Apps의 이전 배포 모델과 Office Web Apps의 새로운 독립 실행형 배포 모델 간의 차이점이 나와 있습니다.

**Office Web Apps 배포 모델 간의 차이점**

![Office Web Apps 서버의 이전 배포 모델과 새로운 독립 실행형 배포 모델의 차이점 표시](images/JJ219437.f16dd9d1-c9b7-4c8b-a8de-f1f82c0ee1e2(Office.15).gif "Office Web Apps 서버의 이전 배포 모델과 새로운 독립 실행형 배포 모델의 차이점 표시")

## SharePoint 2013에서 Office Web Apps 서버를 사용하여 Office 문서를 보고 편집하는 방법

Office Web Apps 서버는 SharePoint Server 2013과 함께 사용하는 경우 업데이트된 Word Web App, Excel Web App, PowerPoint Web App 및 OneNote Web App 버전을 제공합니다. 사용자는 컴퓨터 및 대부분의 모바일 장치(예: Windows Phone, iPhone, iPad, Windows 8 태블릿)에서 지원되는 웹 브라우저를 사용하여 SharePoint 라이브러리의 Office 문서를 볼 수 있으며 일부 경우에는 편집할 수도 있습니다. Office Web Apps에서 새롭게 제공되는 다양한 기능 중에서도, 개선된 터치 지원 및 편집 기능을 사용하면 iPad 및 Windows 8 태블릿 사용자가 장치에서 직접 Office 문서를 편집하고 볼 수 있습니다.

다음 그림에는 여러 유형의 장치에서 사용 가능한 Office Web Apps의 보기 및 편집 기능이 간략하게 나와 있습니다.

**Office Web Apps의 보기 및 편집 기능**

![각 장치 유형에서 제공되는 Office Web Apps의 보기 및 편집 기능이 요약된 그래픽. 터치 스크린에 최적화된 기능을 강조 표시합니다.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "각 장치 유형에서 제공되는 Office Web Apps의 보기 및 편집 기능이 요약된 그래픽. 터치 스크린에 최적화된 기능을 강조 표시합니다.")


> [!NOTE]
> PowerPoint 브로드캐스트는 SharePoint 2013에서 제거되었지만 OneDrive 및 Lync Server 2013에서는 사용할 수 있습니다.



Office Web Apps의 새로운 기능에 대한 자세한 내용은 [Office Web Apps가 SharePoint 2013에서 온-프레미스로 작동하는 방식](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)를 참조하십시오.

## Lync Server 2013에서 Office Web Apps 서버를 사용하여 PowerPoint 브로드캐스트를 보는 방법

Lync Server 2010에서는 두 가지 방식 중 하나로 PowerPoint 프레젠테이션을 볼 수 있었습니다. Lync 2010을 실행하는 사용자의 경우 PowerPoint 프레젠테이션은 PowerPoint 97-2003 형식으로 표시되었으며 내장 PowerPoint Viewer를 통해 볼 수 있었습니다. Lync Web App을 실행하는 사용자의 경우에는 PowerPoint 프레젠테이션이 동적 HTML 파일로 변환된 다음 사용자 지정된 DHTML 파일과 Silverlight를 함께 사용하여 표시되었습니다. 이 방식은 대개 효율적이기는 하지만 다음과 같은 몇 가지 제한이 있었습니다.

  - 최적의 보기 환경을 제공하는 내장 PowerPoint Viewer는 Windows 플랫폼에서만 사용 가능합니다.

  - 널리 사용되는 일부 휴대폰을 비롯한 대부분의 모바일 장치에서는 Silverlight가 지원되지 않습니다.
    
    PowerPoint Viewer 및 DHTML/Silverlight 방식은 화면 전환 및 포함된 비디오를 비롯하여 최신 PowerPoint 버전에서 제공되는 모든 기능을 지원하지 않습니다.

이러한 문제를 해결하고 PowerPoint 프레젠테이션을 진행하거나 보는 모든 사용자의 전반적인 환경을 개선하기 위해, Lync Server 2013에서는 Office Web Apps 서버를 사용하여 PowerPoint 프레젠테이션을 처리합니다. 이와 같은 새로운 방식에는 다양한 이점이 있으며, 특히 다음과 같은 기능이 제공됩니다.

  - 애니메이션, 화면 전환, 포함된 비디오 등의 PowerPoint 기능이 보다 효율적으로 지원되며 보다 높은 해상도의 디스플레이가 제공됩니다.

  - 더 많은 모바일 장치에서 이러한 프레젠테이션에 액세스할 수 있습니다. Lync Server 2013에서는 사용자 지정된 DHTML 및 Silverlight 대신 표준 DHTML 및 JavaScript를 사용하여 PowerPoint 프레젠테이션을 브로드캐스트하기 때문입니다.

  - 적절한 권한이 있는 사용자는 프레젠테이션 자체와는 독립적으로 PowerPoint 프레젠테이션 전체를 스크롤할 수 있습니다. 예를 들어 Ken Myer가 자신의 슬라이드 쇼를 진행하는 중에도 Pilar Ackerman은 Ken의 프레젠테이션에 전혀 영향을 주지 않고 원하는 어떤 슬라이드나 스크롤하고 볼 수 있습니다.

Office Web Apps 서버 를 사용 하 여 Lync Server 2013 구성 하는 방법에 대 한 자세한 내용은 [Office Web Apps 서버를 배포 하 고 Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)을 참조 하십시오.

## Office Web Apps 서버를 통해 사용자가 온라인 뷰어를 사용하여 공유 폴더와 웹 사이트에서 Office 파일을 볼 수 있도록 하는 방법

온라인 뷰어를 통해 사용자는 웹 브라우저에서 조직의 웹 서버 또는 공유 폴더에 저장된 Excel, PowerPoint 및 Word 파일을 볼 수 있습니다. 즉, 별도의 응용 프로그램을 열지 않고도 웹 브라우저에서 Office 파일을 편리하게 볼 수 있습니다. 또한 온라인 뷰어를 사용하는 경우 사용자 컴퓨터에 Office 2013을 설치할 필요가 없습니다. 그뿐만 아니라 온라인 뷰어에서는 웹 페이지 내에 URL을 연결하거나 포함하는 데 필요한 코드도 생성합니다. 온라인 뷰어는 인트라넷이나 인터넷에서 사용할 수 있습니다.

Office Web Apps 서버에서는 http://*OfficeWebAppsServername*/op/generate.aspx 주소에서 페이지를 제공하며, 이 주소를 사용해 UNC 또는 URL 주소가 지정된 공개적으로 사용 가능한 문서에 대한 링크를 생성할 수 있습니다. 사용자가 생성된 URL을 선택하면 온라인 뷰어는 Office Web Apps 서버가 파일을 해당 위치에서 가져온 다음 Office Web Apps를 사용하여 렌더링할 수 있도록 합니다. 사용자는 Office 기능을 계속 사용하면서 Word, Excel 또는 PowerPoint 파일을 브라우저에서 볼 수 있습니다. Word 문서의 서식과 레이아웃은 그대로 유지되고, Excel 통합 문서의 데이터는 필터링 및 정렬할 수 있으며, PowerPoint 프레젠테이션에서는 애니메이션이 재생됩니다. 그러나 온라인 뷰어를 사용하는 경우 파일을 볼 수는 있지만 편집할 수는 없으며 인증이 필요한 파일은 열 수 없습니다.

온라인 뷰어에 대한 자세한 내용은 [온라인 뷰어 계획](plan-office-web-apps-server.md)에서 확인할 수 있습니다.


> [!NOTE]
> Microsoft는 <A href="http://go.microsoft.com/fwlink/?linkid=256548">Office.com</A>에서 인터넷 연결 전용 버전의 URL 만들기를 호스팅합니다.



## 참고 항목


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[Office Web Apps 서버 계획](plan-office-web-apps-server.md)  
[Office Web Apps 서버 배포](deploy-office-web-apps-server.md)  
  

[deploy-office-web-apps-server.md](deploy-office-web-apps-server.md)

