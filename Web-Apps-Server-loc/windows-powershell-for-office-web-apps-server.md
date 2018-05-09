---
title: Office Web Apps Server용 Windows PowerShell
TOCTitle: Office Web Apps Server용 Windows PowerShell
ms:assetid: 56bfd3b3-f563-423d-aea0-65b331f73b96
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Ee890080(v=office.15)
ms:contentKeyID: 49643373
ms.date: 01/04/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Office Web Apps Server용 Windows PowerShell

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2016-12-16_

**요약:** Office Web Apps 서버를 구성하는 OfficeWebApps Windows PowerShell cmdlet 관련 문서를 소개합니다.

**대상:** IT 전문가

Office Web Apps 서버는 브라우저 기반 버전의 Word, PowerPoint, Excel 및 OneNote를 제공하는 새로운 Office 서버 제품입니다. 단일 Office Web Apps 서버 팜이 SharePoint 2013, Lync Server 2013, Exchange Server 2013, 공유 폴더 및 웹 사이트를 통해 Office 파일에 액세스하는 사용자를 지원할 수 있습니다.

![Office 2013 로고](images/Ee855124.a106e261-2cd0-43b7-af77-92de7e4b6fb9(Office.15).png "Office 2013 로고")다음 표에는 Office Web Apps 서버용의 각 OfficeWebApps Windows PowerShell cmdlet과 관련한 문서 및 해당 설명이 나와 있습니다.


> [!TIP]
> Windows PowerShell에서 이러한 cmdlet이 실행될 때 인식하지 못하면 <STRONG>OfficeWebApps</STRONG> 모듈을 가져와야 할 수도 있습니다. 다음 명령을 사용하세요.<BR><CODE>Import-Module -Name OfficeWebApps</CODE>




### OfficeWebApps Windows PowerShell cmdlet

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
<td><p><a href="get-officewebappsfarm.md">Get-OfficeWebAppsFarm</a></p></td>
<td><p>현재 서버가 구성원인 OfficeWebAppsFarm 개체에 대한 세부 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-officewebappshost.md">Get-OfficeWebAppsHost</a></p></td>
<td><p>Office Web Apps 서버 팜의 허용 목록에 있는 호스트 도메인 목록을 반환합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-officewebappsmachine.md">Get-OfficeWebAppsMachine</a></p></td>
<td><p>Office Web Apps 서버 팜에 있는 현재 서버에 대한 세부 정보를 반환합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsfarm.md">New-OfficeWebAppsFarm</a></p></td>
<td><p>로컬 컴퓨터에서 새 Office Web Apps 서버 팜을 만듭니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-officewebappshost.md">New-OfficeWebAppsHost</a></p></td>
<td><p>Office Web Apps 서버 팜의 허용 목록에 호스트 도메인을 추가합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsmachine.md">New-OfficeWebAppsMachine</a></p></td>
<td><p>현재 서버를 기존 Office Web Apps 서버 팜에 추가합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="remove-officewebappshost.md">Remove-OfficeWebAppsHost</a></p></td>
<td><p>Office Web Apps 서버 팜의 허용 목록에서 호스트 도메인을 제거합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="remove-officewebappsmachine.md">Remove-OfficeWebAppsMachine</a></p></td>
<td><p>Office Web Apps 서버 팜에서 현재 서버를 제거합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="repair-officewebappsfarm.md">Repair-OfficeWebAppsFarm</a></p></td>
<td><p>비정상으로 플래그가 지정된 모든 서버를 Office Web Apps 서버 팜에서 제거합니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="set-officewebappsfarm.md">Set-OfficeWebAppsFarm</a></p></td>
<td><p>기존 Office Web Apps 서버 팜의 설정을 구성합니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="set-officewebappsmachine.md">Set-OfficeWebAppsMachine</a></p></td>
<td><p>Office Web Apps 서버 팜에 있는 현재 서버의 설정을 변경합니다.</p></td>
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
<p>Office Web Apps Server에 대해 자세히 알아봅니다.</p>
<ul>
<li><p><a href="deploy-the-infrastructure-office-web-apps-server.md">인프라 배포: Office Web Apps 서버</a></p></li>
</ul>
<p>다음 링크를 통해 Office Server 제품이 Office Web Apps 서버를 사용하여 Office 파일의 웹 기반 보기 및 편집 기능을 제공하는 방법을 확인할 수 있습니다.</p>
<ul>
<li><p><a href="use-office-web-apps-with-sharepoint-2013.md">SharePoint 2013과 함께 Office Web Apps 사용</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256902">Office Web Apps 서버 및 Lync Server 2013 배포</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256611">Office Web Apps 서버 통합(Exchange Server 2013)</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><img src="images/Ee855124.6fa793ee-ede9-4476-901c-de96ea37fc3a(Office.15).png" title="채팅 아이콘" alt="채팅 아이콘" /></p></td>
<td><p><strong>의견 제공</strong></p></td>
<td><p>Office 2013Office 365 ProPlus용 설명서에 대한 의견을 제공하려면 페이지 아래쪽에 있는 <strong>사이트 의견</strong> 링크를 선택합니다. 그러면 의견이 설명서 팀으로 바로 전달됩니다.</p>
<p><img src="images/Ee890080.1863f854-8ce5-40e4-bd40-9bbe16591834(Office.15).png" title="전자 메일" alt="전자 메일" />콘텐츠를 제안하거나, 추가 설명서를 요청하거나, 오류를 보고하려면 <a href="mailto:feedork@microsoft.com">feedork@microsoft.com</a>으로 전자 메일을 보내 주세요.</p></td>
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

