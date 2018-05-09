---
title: Office Web Apps용 Windows PowerShell(SharePoint 2013)
TOCTitle: Office Web Apps용 Windows PowerShell
ms:assetid: eb4b96e4-b12d-43e7-b1ce-fc04f5cbbd31
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219457(v=office.15)
ms:contentKeyID: 49643445
ms.date: 01/04/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Office Web Apps용 Windows PowerShell(SharePoint 2013)

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2016-12-16_

**요약:** Office Web Apps를 구성하는 SPWOPI Windows PowerShell cmdlet 관련 문서를 소개합니다.

**대상:** IT 전문가

Office Web Apps는 온-프레미스에서 SharePoint 2013과 함께 사용하는 경우 업데이트된 Word Web App, Excel Web App, PowerPoint Web App 및 OneNote Web App 버전을 제공합니다. 사용자는 컴퓨터와 다양한 모바일 장치(예: Windows Phone, iPhone, iPad)에서 지원되는 웹 브라우저를 사용하여 Office 문서를 볼 수 있으며 원하는 경우에는 문서를 편집할 수도 있습니다.

![Office 2013 로고](images/Ee855124.a106e261-2cd0-43b7-af77-92de7e4b6fb9(Office.15).png "Office 2013 로고")다음 표에는 SharePoint 2013과 함께 사용할 수 있도록 Office Web Apps를 구성하는 각 SPWOPI Windows PowerShell cmdlet과 관련한 문서 및 해당 설명이 나와 있습니다.


### SPWOPI Windows PowerShell cmdlet

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>문서</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="get-spwopibinding.md">Get-SPWOPIBinding</a></p></td>
<td><p>이 cmdlet을 실행하는 현재 SharePoint 팜에서 <strong>New-SPWOPIBinding</strong>을 사용하여 작성된 바인딩 목록을 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-spwopisuppressionsetting.md">Get-SPWOPISuppressionSetting</a></p></td>
<td><p>이 cmdlet을 실행하는 현재 SharePoint 팜에서 비표시 설정을 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-spwopizone.md">Get-SPWOPIZone</a></p></td>
<td><p>사용할 WOPI 응용 프로그램에 대해 현재 SharePoint 팜에 구성되어 있는 영역을 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-spwopibinding.md">New-SPWOPIBinding</a></p></td>
<td><p>이 cmdlet을 실행하는 현재 SharePoint 팜에서 파일 이름 확장명 또는 응용 프로그램을 작업과 연결하는 새 바인딩을 만듭니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-spwopisuppressionsetting.md">New-SPWOPISuppressionSetting</a></p></td>
<td><p>현재 SharePoint 팜에 대해 지정한 작업 및 문서 유형이나 바인딩에 대해 Office Web Apps를 해제합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="remove-spwopibinding.md">Remove-SPWOPIBinding</a></p></td>
<td><p>이 cmdlet을 실행하는 현재 SharePoint 팜에서 응용 프로그램, 파일 이름 확장명 및 연결된 해당 작업에 대한 바인딩을 제거합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="remove-spwopisuppressionsetting.md">Remove-SPWOPISuppressionSetting</a></p></td>
<td><p>이 cmdlet을 실행하는 현재 SharePoint 팜에서 파일 형식 또는 ProgID(프로그램 ID)에 대한 비표시 설정을 제거합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="set-spwopibinding.md">Set-SPWOPIBinding</a></p></td>
<td><p>응용 프로그램 또는 파일 이름 확장명 바인딩에 대한 기본 클릭 작업을 업데이트합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="set-spwopizone.md">Set-SPWOPIZone</a></p></td>
<td><p>현재 SharePoint 팜이 브라우저를 탐색하여 WOPI 응용 프로그램으로 이동하는 데 사용할 영역을 구성합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="update-spwopiproofkey.md">Update-SPWOPIProofKey</a></p></td>
<td><p>이 cmdlet을 실행하는 현재 SharePoint 팜에서 WOPI 응용 프로그램에 연결하는 데 사용되는 공용 키를 업데이트합니다.</p></td>
</tr>
</tbody>
</table>


### IT 전문가용 기타 Office 리소스

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/Ee855124.22cad0f4-303d-4a40-90a3-fa08e69dfdaf(Office.15).png" title="새 소식 아이콘(상자)" alt="새 소식 아이콘(상자)" /></p></td>
<td><p><strong>신규 게시 콘텐츠</strong></p></td>
<td><p>새로 게시되었거나 최근에 업데이트된 Office Web Apps 서버 문서의 목록을 확인하려면 다음 문서를 참조하십시오.</p>
<ul>
<li><p><a href="https://technet.microsoft.com/ko-kr/library/ff433481(v=office.15)">새로 게시된 Office Web Apps 및 Office Web Apps Server 관련 콘텐츠</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><img src="images/Ee855124.6b2d6dfa-7dc8-40fb-8335-af68b575f8cb(Office.15).png" title="시작" alt="시작" /></p></td>
<td><p><strong>시작</strong></p></td>
<td><p>Office Web Apps 서버를 다운로드합니다.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256561">VLSC(볼륨 라이선스 서비스 센터)</a></p>
<p>Office Web Apps 서버를 다운로드하려면 볼륨 라이선스 계약에 따라 Office Professional Plus 2013, Office Standard 2013 또는 Office for Mac 2011에 대한 라이선스가 있어야 합니다. 다운로드 위치는 VLSC 포털에서 해당 Office 제품 아래에 있습니다.</p></li>
</ul>
<p>Office Web Apps 서버용 언어 팩을 다운로드합니다.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=263945">Microsoft 다운로드 센터</a></p></li>
</ul>
<p>Office Web Apps 서버에 대해 자세히 설명합니다.</p>
<ul>
<li><p><a href="deploy-the-infrastructure-office-web-apps-server.md">인프라 배포: Office Web Apps 서버</a></p></li>
</ul>
<p>다음 링크를 통해 Office Server 제품이 Office Web Apps 서버를 사용하여 Office 파일의 웹 기반 보기 및 편집 기능을 제공하는 방법을 확인할 수 있습니다.</p>
<ul>
<li><p><a href="use-office-web-apps-with-sharepoint-2013.md">SharePoint 2013과 함께 Office Web Apps 사용</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><img src="images/Ee855124.6fa793ee-ede9-4476-901c-de96ea37fc3a(Office.15).png" title="채팅 아이콘" alt="채팅 아이콘" /></p></td>
<td><p><strong>의견 제공</strong></p></td>
<td><p>Office 2013Office 365 ProPlus용 설명서에 대한 의견을 제공하려면 페이지 아래쪽에 있는 <strong>사이트 의견</strong> 링크를 선택합니다. 그러면 의견이 설명서 팀으로 바로 전달됩니다.</p></td>
</tr>
</tbody>
</table>


## Office 관련 교육 및 기타 리소스 찾기


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Download</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/evalcenter/hh973391">Office 365 ProPlus</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/p/?linkid=507653">Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/evalcenter/ee390818.aspx">Office 2013</a></p></li>
<li><p><a href="https://code.msdn.microsoft.com/office/">Office 코드 샘플</a></p></li>
<li><p><a href="https://gallery.technet.microsoft.com/office/">Office 스크립트 및 샘플 파일</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/office/aa905351">Office 개발자 다운로드</a></p></li>
<li><p><a href="http://www.microsoft.com/download/ko/office.aspx?q=office">Office 다운로드</a></p></li>
<li><p><a href="http://www.microsoft.com/ko-kr/download/search.aspx?q=office+365">Office 365 다운로드</a></p></li>
</ul></td>
<td><p><strong>방법</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/ko-kr/library/jj220060.aspx">Office용 앱 구축</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/library/cc178982.aspx">Office 2013 배포</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/library/cc179068.aspx">Office 2013 관리</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/office/ff381682.aspx">Office 2010 최종 사용자 교육</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/office/aa905496.aspx">Office Sdk</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/office/aa905375">Office 개발자 교육</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/ko-kr/office/media/video/video.html?cid=odc%26from=mscomodc">Office 개발자 동영상</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/ko-kr/office/media/video/video.html?cid=o365%26from=mscomo365">Office 365 개발자 동영상</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/office/ff519671">Office IT 전문가 교육</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technetko-kr/office/media/video/video.html?cid=otc%26from=mscomotc">Office IT 전문가 동영상</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technet/ko-kr/office/media/video/video.html?cid=o365%26from=mscomo365">Office 365 IT 전문가 동영상</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/openspecifications/">사양 열기</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/library/cc307282(v=office.12).aspx">Office 프로토콜</a></p></li>
</ul></td>
<td><p><strong>Sites</strong></p>
<ul>
<li><p><a href="https://msdn.microsoft.com/ko-kr/office">Office 개발자</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/office">Office IT 전문가</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/office/hh506337">Office 365 개발자</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/hh912691">Office 365 IT 전문가</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/library/cc303401.aspx">Office 2013 Resource Kit</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/sharepoint">SharePoint 개발자</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/sharepoint">SharePoint IT 전문가</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/vstudio/aa718325">Visual Studio 개발자</a></p></li>
<li><p><a href="http://office.microsoft.com/">Office.com</a></p></li>
</ul></td>
<td><p><strong>Help</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/ko-kr/office/ee748587.aspx">Office 업데이트</a></p></li>
<li><p><a href="https://blogs.msdn.com/b/officeapps">Office 및 SharePoint용 앱 블로그</a></p></li>
<li><p><a href="https://social.msdn.microsoft.com/forums/ko-kr/category/officedev%2coldevelopment%2csharepoint2010%2csharepoint%2cprojectserver2010%2cprojectprofessional2010%2cuc/">포럼: 개발자용 Office</a></p></li>
<li><p><a href="https://answers.microsoft.com/ko-kr/msoffice">포럼: Office 365</a></p></li>
<li><p><a href="https://social.technet.microsoft.com/wiki">TechNet Wiki</a></p></li>
<li><p><a href="https://stackoverflow.com/search?q=office">StackOverflow: Office</a></p></li>
<li><p><a href="https://mvp.microsoft.com/ko-kr/mvp/search-mvp.aspx?kw=office">Office MVP</a></p></li>
<li><p><a href="https://technet.microsoft.com/ko-kr/ms772425">Office IT 전문가 지원</a></p></li>
<li><p><a href="https://msdn.microsoft.com/ko-kr/office/aa905515">Office 개발자 지원</a></p></li>
</ul></td>
</tr>
</tbody>
</table>


[](use-office-web-apps-with-sharepoint-2013.md)

