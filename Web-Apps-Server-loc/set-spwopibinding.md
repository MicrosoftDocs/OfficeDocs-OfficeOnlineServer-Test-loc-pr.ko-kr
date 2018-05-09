---
title: Set-SPWOPIBinding
TOCTitle: Set-SPWOPIBinding
ms:assetid: e373528f-e69b-4e25-9df4-3a5f80ab64ac
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219454(v=office.15)
ms:contentKeyID: 49643438
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIBinding

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2015-03-09_

응용 프로그램 또는 파일 이름 확장명 바인딩에 대한 기본 클릭 작업을 업데이트합니다.

## 구문

    Set-SPWOPIBinding [-Identity] <SPWopiBindingPipeBind> -DefaultAction <SwitchParameter> [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Set-SPWOPIBinding** cmdlet은 응용 프로그램 또는 파일 이름 확장명 바인딩에 대한 기본 클릭 작업을 업데이트합니다. 예를 들어 SharePoint 라이브러리에서 Word 문서를 보기 위한 기본 클릭 작업을 설정할 수 있습니다. 이렇게 하려면 “view”-“Word” 바인딩에 대해 기본 작업을 true로 설정합니다.

일반적으로 **Get-SPWOPIBinding** 명령의 결과를 이 명령의 -Identity 속성 값으로 사용합니다. 자세한 내용은 [Get-SPWOPIBinding](get-spwopibinding.md)을 참조하세요.


> [!IMPORTANT]
> <STRONG>New-SPWOPIBinding</STRONG> 명령을 사용하여 만든 바인딩만 설정할 수 있습니다. 예를 들어 SharePoint 라이브러리의 Word 문서를 볼 때 수행되는 작업과 같은 기본 제공 바인딩을 재정의하려면 <STRONG>New-SPWOPIBinding</STRONG>을 사용하여 새 바인딩을 만들고 다른 작업을 할당합니다. 자세한 내용은 <A href="new-spwopibinding.md">New-SPWOPIBinding</A>을 참조하세요.



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
<td><p>필수</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>바인딩을 지정합니다. 일반적으로 <strong>Get-SPWOPIBinding</strong> 명령의 결과를 –Identity의 값으로 사용합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DefaultAction</strong></p></td>
<td><p>필수</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>바인딩의 응용 프로그램 또는 파일 이름 확장명에 대해 바인딩을 기본 클릭 작업으로 설정할지 여부를 지정합니다.</p></td>
</tr>
<tr class="odd">
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
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WhatIf</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하는 대신에 명령의 효과를 설명하는 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
</tbody>
</table>


## 입력 형식

## 반환 형식

## 예제

\---------------예제---------------

    Get-SPWOPIBinding -Action "view" -Application "Word"| Set-SPWOPIBinding -DefaultAction

이 예제에서는 SharePoint 라이브러리에서 Word 문서를 보기 위한 기본 클릭 작업을 설정합니다. **Get-SPWOPIBinding ?Action “view” ?Application “Word”** cmdlet을 실행하여 기본 클릭 작업이 Word 보기로 설정되어 있는지 확인할 수 있습니다. **IsDefaultAction** 값은 “True”로 설정됩니다.

## 참고 항목


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  
[New-SPWOPIBinding](new-spwopibinding.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 Office Web Apps 사용](use-office-web-apps-with-sharepoint-2013.md)

