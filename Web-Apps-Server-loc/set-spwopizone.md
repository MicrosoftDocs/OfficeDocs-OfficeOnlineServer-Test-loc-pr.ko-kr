---
title: Set-SPWOPIZone
TOCTitle: Set-SPWOPIZone
ms:assetid: bc751cc4-8ac8-45f7-b6ea-da6fcb5473ac
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219451(v=office.15)
ms:contentKeyID: 49643424
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIZone

 

_**적용 대상:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:**2015-03-09_

현재 SharePoint 팜이 브라우저를 탐색하여 WOPI 응용 프로그램으로 이동하는 데 사용할 영역을 구성합니다.

## 구문

    Set-SPWOPIZone [[-Zone] <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Set-SPWOPIZone** cmdlet은 현재 SharePoint 팜이 브라우저를 탐색하여 WOPI 응용 프로그램(예: Office Web Apps 서버 실행 서버)으로 이동하는 데 사용할 영역을 구성합니다. 브라우저의 SharePoint Server 페이지는 WOPI 응용 프로그램의 페이지를 포함하는 프레임을 만듭니다. WOPI 응용 프로그램 페이지 URL의 영역은 이 설정을 통해 결정됩니다.

영역을 설정하지 않으면 기본적으로 “internal-HTTPS”가 사용됩니다. WOPI 응용 프로그램에서 지원하지 않는 영역을 선택하면 Office Web Apps가 작동하지 않습니다. IPSEC(전체 암호화)을 사용하는 완전 보안 네트워크 또는 중요한 데이터를 포함하지 않는 테스트 환경에서만 HTTP를 사용하십시오.

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
<td><p><strong>Zone</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>영역을 지정합니다. WOPI 응용 프로그램에서 지원하는 영역 목록의 경우 <strong>Get-SPWOPIBinding</strong>을 실행합니다.</p>
<p>내부 및 외부용으로 모두 사용되는 SharePoint 팜의 경우에는 외부를 지정합니다. 내부 전용 SharePoint 팜의 경우에는 내부를 지정합니다. IPSEC(전체 암호화)을 사용하는 완전 보안 네트워크 또는 중요한 데이터를 포함하지 않는 테스트 환경에서만 HTTP를 사용하십시오. 옵션은 다음과 같습니다.</p>
<p>- Internal-HTTP</p>
<p>- Internal-HTTPS</p>
<p>- External-HTTP</p>
<p>- External-HTTPS</p></td>
</tr>
<tr class="even">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>선택</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>올바른 삭제를 위해 개체를 관리합니다. <strong>SPWeb</strong> 또는 <strong>SPSite</strong>와 같은 개체를 사용하는 경우 많은 양의 메모리를 사용할 수 있으며, Windows PowerShell 스크립트에서 이러한 개체를 사용하려면 올바른 메모리 관리가 필요합니다. <strong>SPAssignment</strong> 개체를 사용하면 개체를 하나의 변수에 지정하고 해당 개체가 필요한 시기가 지나면 개체를 삭제하여 메모리를 확보할 수 있습니다. <strong>SPWeb</strong>, <strong>SPSite</strong> 또는 <strong>SPSiteAdministration</strong> 개체를 사용하는 경우 지정 컬렉션 또는 <strong>Global</strong> 매개 변수가 사용되지 않으면 해당 개체가 자동으로 삭제됩니다.</p>
<div class="alert">

> [!NOTE]
> <STRONG>Global</STRONG> 매개 변수가 사용되는 경우 모든 개체가 전역 저장소에 포함됩니다. 개체가 즉시 사용되지 않거나 <STRONG>Stop-SPAssignment</STRONG> 명령을 사용하여 삭제되지 않는 경우 메모리 부족 시나리오가 발생할 수 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="even">
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

    Set-SPWOPIZone -Zone "external-https"

이 예제에서는 HTTPS를 통해 WOPI 응용 프로그램(예: Office Web Apps 서버 실행 서버)으로의 외부 연결을 사용하도록 현재 SharePoint 팜을 구성합니다.

## 참고 항목


[Get-SPWOPIZone](get-spwopizone.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[SharePoint 2013과 함께 Office Web Apps 사용](use-office-web-apps-with-sharepoint-2013.md)

