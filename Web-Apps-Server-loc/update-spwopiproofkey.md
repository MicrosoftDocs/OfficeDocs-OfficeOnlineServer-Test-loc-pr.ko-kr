---
title: Update-SPWOPIProofKey
TOCTitle: Update-SPWOPIProofKey
ms:assetid: fe7f3a87-082e-4a43-a5f3-7be41d8e91a3
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219460(v=office.15)
ms:contentKeyID: 49643449
ms.date: 12/19/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Update-SPWOPIProofKey

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2015-03-09_

이 cmdlet을 실행하는 현재 SharePoint 팜에서 WOPI 응용 프로그램에 연결하는 데 사용되는 공용 키를 업데이트합니다.

## 구문

    Update-SPWOPIProofKey [-AssignmentCollection <SPAssignmentCollection>] [-ServerName <String>]

## 자세한 정보

**Update-SPWOPIProofKey** cmdlet은 이 cmdlet을 실행하는 현재 SharePoint 팜에서 WOPI 응용 프로그램(Office Web Apps 서버 실행 서버일 수 있음)에 연결하는 데 사용되는 공용 키를 업데이트합니다. SharePoint 팜과 WOPI 응용 프로그램 간에 키가 동기화되지 않는 경우 이 cmdlet을 사용할 수 있습니다. 키가 동기화되지 않으면 문서가 브라우저에서 열리지 않으며 "파일에 대해 증명 서명이 잘못됨..." 또는 "폴더에 대해 증명 서명이 잘못됨..."과 같은 메시지가 ULS(통합 로깅 시스템) 로그에 포함됩니다.

SharePoint 관리 셸

## 매개 변수


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>매개 변수</th>
<th>필수</th>
<th>형식</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>선택</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>올바른 삭제를 위해 개체를 관리합니다. <strong>SPWeb</strong> 또는 <strong>SPSite</strong>와 같은 개체를 사용하는 경우 많은 양의 메모리를 사용할 수 있으며, Windows PowerShell 스크립트에서 이러한 개체를 사용하려면 올바른 메모리 관리가 필요합니다. <strong>SPAssignment</strong> 개체를 사용하면 개체를 하나의 변수에 지정하고 해당 개체가 필요한 시기가 지나면 개체를 삭제하여 메모리를 확보할 수 있습니다. <strong>SPWeb</strong>, <strong>SPSite</strong> 또는 <strong>SPSiteAdministration</strong> 개체를 사용하는 경우 지정 컬렉션 또는 <strong>Global</strong> 매개 변수가 사용되지 않으면 해당 개체가 자동으로 삭제됩니다.</p>
<div class="alert">

> [!NOTE]
> <STRONG>Global</STRONG> 매개 변수가 사용되는 경우 모든 개체가 전역 저장소에 포함됩니다. 개체가 즉시 사용되지 않거나 <STRONG>Stop-SPAssignment</STRONG> 명령을 사용하여 삭제되지 않는 경우 메모리 부족 시나리오가 발생할 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p><strong>ServerName</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>키를 가져올 WOPI 응용 프로그램을 지정합니다. WOPI 응용 프로그램은 Office Web Apps 서버를 실행하는 서버일 수 있습니다. 이 매개 변수가 없으면 현재 SharePoint 팜에 연결된 모든 WOPI 응용 프로그램의 공용 키가 업데이트됩니다.</p></td>
</tr>
</tbody>
</table>


## 입력 형식

## 반환 형식

## 예제

\---------------예제---------------

    Update-SPWOPIProofKey -ServerName "Server.corp.Contoso.com"

이 예제에서는 Office Web Apps 서버 실행 서버와 같은 WOPI 응용 프로그램에서 현재 공용 키를 가져온 다음 SharePoint 팜에 저장된 키를 업데이트합니다.

## 참고 항목


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 Office Web Apps 사용](use-office-web-apps-with-sharepoint-2013.md)

