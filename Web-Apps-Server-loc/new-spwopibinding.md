---
title: New-SPWOPIBinding
TOCTitle: New-SPWOPIBinding
ms:assetid: 696f01b4-a144-431b-9bae-1c3ede78609d
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219441(v=office.15)
ms:contentKeyID: 49643377
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPIBinding

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2015-03-09_

이 cmdlet을 실행하는 현재 SharePoint 팜에서 파일 이름 확장명 또는 응용 프로그램을 작업과 연결하는 새 바인딩을 만듭니다.

## 구문

    New-SPWOPIBinding -ServerName <String> [-Action <String>] [-AllowHTTP <SwitchParameter>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-FileName <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**New-SPWOPIBinding** cmdlet은 이 cmdlet을 실행하는 현재 SharePoint 팜에서 파일 이름 확장명 또는 응용 프로그램을 작업에 연결합니다. 각 바인딩을 통해 WOPI 응용 프로그램을 사용하여 SharePoint 라이브러리의 파일을 보거나 편집할 수 있습니다. 예를 들어 사용자가 SharePoint 문서 목록에서 Word 문서를 볼 때는 해당 SharePoint 팜에서 Word에 바인딩된 작업을 기반으로 문서를 보거나 편집하는 데 사용할 수 있는 옵션이 SharePoint 목록에 표시됩니다.

Office Web Apps에 대해 Office Web Apps 서버 실행 서버와 같은 WOPI 응용 프로그램을 사용하려면 SharePoint 팜에서 이 cmdlet을 실행해야 Office Web Apps를 사용할 수 있습니다.

바인딩 또는 연결이 이미 있는 응용 프로그램이나 파일 이름 확장명에 대해 **New-SPWOPIBinding**을 실행하면 cmdlet이 실패합니다.

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
<td><p><strong>ServerName</strong></p></td>
<td><p>필수</p></td>
<td><p>System.String</p></td>
<td><p>Office Web Apps 서버 실행 서버와 같은 WOPI 응용 프로그램의 이름 또는 FQDN(정규화된 도메인 이름)을 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩할 작업을 &quot;view&quot;, &quot;edit&quot;, &quot;embedview&quot; 등과 같이 지정합니다. WOPI 응용 프로그램에서 지원하는 작업 목록의 경우 <strong>Get-SPWOPIBinding</strong>을 실행합니다. 일반적으로는 이 매개 변수를 사용하지 않습니다. 일부 작업만 지정하는 경우에는 일부 SharePoint 기능이 작동하지 않을 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHTTP</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>cmdlet이 WOPI 응용 프로그램이 지원하는 항목을 검색하는 데 HTTP를 사용할 수 있도록 지정합니다. True로 지정하는 경우 안전하지 않은 연결을 통해 WOPI 응용 프로그램의 검색 정보를 보냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩할 응용 프로그램을 지정합니다. 지정 가능한 응용 프로그램은 “Word&quot;, “Excel&quot;, “PowerPoint&quot; 또는 “OneNote&quot;입니다. WOPI 응용 프로그램에서 지원하는 전체 응용 프로그램 목록을 가져오려면 <strong>Get-SPWOPIBinding</strong>을 실행합니다.</p></td>
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
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩할 파일 이름 확장명을 지정합니다. WOPI 응용 프로그램에서 지원하는 파일 이름 확장명 목록을 가져오려면 <strong>Get-SPWOPIBinding</strong>을 실행합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileName</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>WOPI 응용 프로그램의 검색 정보를 포함하는 xml 파일의 경로를 지정합니다. 검색 정보를 WOPI 응용 프로그램에서 직접 요청하는 대신 xml 파일에서 로드할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>바인딩할 응용 프로그램의 ProgID(프로그래밍 ID)를 지정합니다. WOPI 응용 프로그램에서 지원하는 ProgID 목록을 가져오려면 <strong>Get-SPWOPIBinding</strong>을 실행합니다. OneNote 폴더에 작업을 연결하려는 경우에만 이 매개 변수를 사용합니다.</p></td>
</tr>
<tr class="even">
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

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com"

이 예제에서는 이 cmdlet을 실행하는 현재 SharePoint 팜에서 WOPI 응용 프로그램이 지원하는 모든 응용 프로그램 및 파일 이름 확장명에 대한 바인딩을 만듭니다.

\---------------예제 2---------------

    New-SPWOPIBinding -ServerName "Server.corp.Contoso.com" -Application "Excel"

이 예제에서는 이 cmdlet을 실행하는 현재 SharePoint 팜에서 WOPI 응용 프로그램이 Excel에 대해 지원하는 모든 작업을 Excel에 연결합니다.

## 참고 항목


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 Office Web Apps 사용](use-office-web-apps-with-sharepoint-2013.md)

