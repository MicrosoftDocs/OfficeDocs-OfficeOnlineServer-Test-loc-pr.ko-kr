---
title: Remove-SPWOPISuppressionSetting
TOCTitle: Remove-SPWOPISuppressionSetting
ms:assetid: cbaef5a8-e682-4166-be44-15ab1c79acca
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219452(v=office.15)
ms:contentKeyID: 49643433
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-SPWOPISuppressionSetting

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2015-03-09_

이 cmdlet을 실행하는 현재 SharePoint 팜에서 파일 이름 확장명 또는 프로그래밍 ID와 작업에 대한 비표시 설정을 제거합니다.

## 구문

    Remove-SPWOPISuppressionSetting [-Action <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

    Remove-SPWOPISuppressionSetting [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Identity <String>] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Remove-SPWOPISuppressionSetting** cmdlet은 이 cmdlet을 실행하는 현재 SharePoint 팜에서 파일 이름 확장명 또는 ProgID(프로그래밍 ID)와 작업에 대한 비표시 설정을 제거합니다.

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
<td><p>지정된 파일 이름 확장명 또는 ProgId(프로그래밍 ID)에 대한 작업을 “view”, “edit”, “embedview” 등으로 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>선택</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>올바른 삭제를 위해 개체를 관리합니다. <strong>SPWeb</strong> 또는 <strong>SPSite</strong>와 같은 개체를 사용하는 경우 많은 양의 메모리를 사용할 수 있으며, Windows PowerShell 스크립트에서 이러한 개체를 사용하려면 올바른 메모리 관리가 필요합니다. <strong>SPAssignment</strong> 개체를 사용하면 개체를 하나의 변수에 지정하고 해당 개체가 필요한 시기가 지나면 개체를 삭제하여 메모리를 확보할 수 있습니다. <strong>SPWeb</strong>, <strong>SPSite</strong> 또는 <strong>SPSiteAdministration</strong> 개체를 사용하는 경우 지정 컬렉션 또는 <strong>Global</strong> 매개 변수가 사용되지 않으면 해당 개체가 자동으로 삭제됩니다.</p>
<div class="alert">

> [!NOTE]
> <STRONG>Global</STRONG> 매개 변수가 사용되는 경우 모든 개체가 전역 저장소에 포함됩니다. 개체가 즉시 사용되지 않거나 <STRONG>Stop-SPAssignment</STRONG> 명령을 사용하여 삭제되지 않는 경우 메모리 부족 시나리오가 발생할 수 있습니다.


</div>
<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Extension</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>파일 이름 확장명을 지정합니다. WOPI 응용 프로그램에서 지원하는 파일 이름 확장명 목록을 가져오려면 Get-SPWOPIBinding을 실행합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>SPWOPISuppressionSetting을 나타내는 문자열을 지정합니다. 그러한 문자열의 예를 확인하려면 Get-SPWOPISuppressionSetting을 실행합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgId</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>응용 프로그램에 대해 표시하지 않을 ProgID(프로그래밍 ID)를 지정합니다. WOPI 응용 프로그램에서 지원하는 ProgID 목록을 가져오려면 Get-SPWOPIBinding을 실행합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WhatIf</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하는 대신에 명령의 효과를 설명하는 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## 입력 형식

## 반환 형식

## 예제

\---------------예제 1---------------

    Remove-SPWOPISuppressionSetting -Extension "XLSX" -Action "view"

이 예제에서는 파일 이름 확장명이 “.xlsx”인 Excel 통합 문서를 보기 위한 비표시 설정을 제거합니다.

\---------------예제 2---------------

    Get-SPWOPISuppressionSetting | Remove-SPWOPISuppressionSetting

이 예제에서는 이 cmdlet을 실행하는 현재 SharePoint 팜에서 모든 비표시 설정을 제거합니다.

## 참고 항목


[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  
[Get-SPWOPISuppressionSetting](get-spwopisuppressionsetting.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 Office Web Apps 사용](use-office-web-apps-with-sharepoint-2013.md)

