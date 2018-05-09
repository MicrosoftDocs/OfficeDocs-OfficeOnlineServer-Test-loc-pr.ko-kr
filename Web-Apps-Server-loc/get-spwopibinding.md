---
title: Get-SPWOPIBinding
TOCTitle: Get-SPWOPIBinding
ms:assetid: b757301b-f6c5-43a5-a8ca-2ef33ede0ae8
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219450(v=office.15)
ms:contentKeyID: 49643423
ms.date: 12/19/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPIBinding

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2015-03-09_

이 cmdlet을 실행하는 현재 SharePoint 팜에서 **New-SPWOPIBinding**을 사용하여 작성된 바인딩 목록을 반환합니다.

## 구문

    Get-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WOPIZone <String>]

## 자세한 정보

**Get-SPWOPIBinding**은 이 cmdlet을 실행하는 현재 SharePoint 팜에서 **New-SPWOPIBinding**을 사용하여 작성된 바인딩 목록을 반환합니다. 결과에는 WOPI 응용 프로그램(예: Office Web Apps 서버 실행 서버)에 대해 구성된 영역, 파일 형식, 응용 프로그램 및 작업이 포함됩니다.

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
<td><p><strong>Action</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 반환할 작업을 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 반환할 응용 프로그램을 지정합니다.</p></td>
</tr>
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
<td><p><strong>Extension</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 반환할 파일 이름 확장명을 지정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 반환할 응용 프로그램의 ProgID(프로그래밍 ID)를 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 반환할 WOPI 응용 프로그램(예: Office Web Apps 서버 실행 서버)의 이름을 지정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 반환할 영역을 지정합니다.</p></td>
</tr>
</tbody>
</table>


## 입력 형식

## 반환 형식

## 예제

\---------------예제 1---------------

    Get-SPWOPIBinding -Server "Server.corp.Contoso.com"

이 예제에서는 WOPI 응용 프로그램 "Server.corp.Contoso.com"에 대해 이 cmdlet이 실행되는 현재 SharePoint 팜에서 작성된 바인딩 목록을 반환합니다. WOPI 응용 프로그램은 Office Web Apps 서버를 실행하는 서버일 수 있습니다.

\---------------예제 2---------------

    Get-SPWOPIZone | Get-SPWOPIBinding

이 예제에서는 WOPI 응용 프로그램용으로 구성된 영역에 대해 이 cmdlet을 실행하는 현재 SharePoint 팜에서 작성된 바인딩 목록을 반환합니다.

## 참고 항목


[New-SPWOPIBinding](new-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 Office Web Apps 사용](use-office-web-apps-with-sharepoint-2013.md)

