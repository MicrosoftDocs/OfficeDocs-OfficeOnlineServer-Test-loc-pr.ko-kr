---
title: Remove-SPWOPIBinding
TOCTitle: Remove-SPWOPIBinding
ms:assetid: 52855c21-ee2c-497a-b308-bf5eeabe4bbe
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219438(v=office.15)
ms:contentKeyID: 49643372
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-SPWOPIBinding

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2015-03-09_

이 cmdlet을 실행하는 현재 SharePoint 팜에서 응용 프로그램, 파일 이름 확장명 및 연결된 해당 작업에 대한 바인딩을 제거합니다.

## 구문

    Remove-SPWOPIBinding [[-Identity] <SPWopiBindingPipeBind>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

    Remove-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WhatIf [<SwitchParameter>]] [-WOPIZone <String>]

    Remove-SPWOPIBinding [-All <SwitchParameter>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Remove-SPWOPIBinding** cmdlet은 이 cmdlet을 실행하는 현재 SharePoint 팜에서 응용 프로그램, 파일 이름 확장명 및 연결된 해당 작업에 대한 바인딩을 제거합니다. 이 cmdlet을 실행한 후 **New-SPWOPIBinding**을 사용하여 필요에 따라 바인딩을 다시 만들 수 있습니다. 응용 프로그램에 대한 모든 바인딩을 제거하면 사용자가 해당 응용 프로그램에 대해 Office Web Apps 또는 SharePoint의 링크로 공유 기능을 사용할 수 없습니다. 이 cmdlet을 실행하는 SharePoint 팜에서 모든 바인딩을 제거하면 사용자가 SharePoint 라이브러리의 모든 응용 프로그램에 대해 Office Web Apps 또는 SharePoint의 링크로 공유 기능을 사용할 수 없습니다.

기본 클릭에 대해 Office Web Apps는 더 이상 사용하지 않지만 바인딩의 검색 정보와 사용자가 SharePoint의 링크로 공유 기능을 사용하여 문서 링크를 보낸 다음 받는 사람이 해당 문서 종류에 대해 Office Web Apps를 사용하도록 허용하는 기능은 유지하려면 **New-SPWOPISuppression** cmdlet을 대신 사용합니다.

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
<td><p><strong>Identity</strong></p></td>
<td><p>선택</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>바인딩을 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 제거할 작업을 &quot;view&quot;, &quot;edit&quot;, &quot;embedview&quot; 등과 같이 지정합니다. 작업 목록의 경우 <strong>Get-SPWOPIBinding</strong>을 실행합니다. 일반적으로는 이 매개 변수를 사용하지 않습니다. 일부 작업만 지정하는 경우에는 SharePoint의 일부 기능이 작동하지 않을 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>모든 바인딩을 제거합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 제거할 응용 프로그램을 지정합니다. 지정 가능한 응용 프로그램은 “Word&quot;, “Excel&quot;, “PowerPoint&quot; 또는 “OneNote&quot;입니다. 응용 프로그램 목록을 가져오려면 <strong>Get-SPWOPIBinding</strong>을 실행합니다.</p></td>
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
<td><p><strong>Confirm</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 제거할 파일 이름 확장명을 지정합니다. 파일 이름 확장명 목록을 가져오려면 <strong>Get-SPWOPIBinding</strong>을 실행합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgId</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 제거할 응용 프로그램의 ProgID(프로그래밍 ID)를 지정합니다. ProgID 목록을 가져오려면 <strong>Get-SPWOPIBinding</strong>을 실행합니다. OneNote에 대한 바인딩을 제거하려는 경우에만 이 매개 변수를 사용할 수도 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>Office Web Apps 서버 등 바인딩을 제거할 WOPI 응용 프로그램의 이름을 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하는 대신에 명령의 효과를 설명하는 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩을 제거할 영역을 지정합니다.</p></td>
</tr>
</tbody>
</table>


## 입력 형식

## 반환 형식

## 예제

\---------------예제 1---------------

    Remove-SPWOPIBinding -Application "Excel"

이 예제에서는 이 cmdlet을 실행하는 현재 SharePoint 팜에서 Excel에 대한 모든 바인딩을 제거합니다.

\--------------예제 2-----------------

    Remove-SPWOPIBinding -All:$true

이 예제에서는 이 cmdlet을 실행하는 현재 SharePoint 팜에서 모든 바인딩을 제거합니다.

\--------------예제 3-----------------

    Get-SPWOPIBinding -Action "MobileView" | Remove-SPWOPIBinding

이 예제에서는 이 cmdlet을 실행하는 현재 SharePoint 팜에서 Office Mobile Web Apps에 대한 모든 바인딩을 제거합니다.

## 참고 항목


[New-SPWOPIBinding](new-spwopibinding.md)  
[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 Office Web Apps 사용](use-office-web-apps-with-sharepoint-2013.md)

