---
title: New-OfficeWebAppsMachine
TOCTitle: New-OfficeWebAppsMachine
ms:assetid: b0385c4e-61fc-4607-a48c-64d8f4e80651
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219449(v=office.15)
ms:contentKeyID: 49643422
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsMachine

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2015-03-09_

현재 서버를 기존 Office Web Apps 서버 팜에 추가합니다.

## 구문

    New-OfficeWebAppsMachine [-MachineToJoin] <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**New-OfficeWebAppsMachine** cmdlet은 현재 서버를 기존 Office Web Apps 서버 팜에 추가하고 필요에 따라 새 서버에서 하나 이상의 역할을 설정합니다.

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
<td><p><strong>MachineToJoin</strong></p></td>
<td><p>필수</p></td>
<td><p>System.String</p></td>
<td><p>이미 Office Web Apps 서버 팜의 구성원인 서버의 이름을 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>사용자 프롬프트에 대한 모든 대답이 예라고 가정합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Roles</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String[]</p></td>
<td><p>새 서버에 할당할 하나 이상의 서버 역할을 쉼표로 구분하여 지정합니다. 역할을 지정하지 않으면 서버에 모든 역할이 할당됩니다.</p>
<p>역할 유형은 다음과 같습니다.</p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">

> [!IMPORTANT]
> Office Web Apps 서버 팜의 모든 서버에서 모든 역할을 실행하는 것이 가장 좋습니다. Office Web Apps 서버 팜에 서버가 50개 정도 포함되어야 역할 할당을 통한 이점을 얻을 수 있습니다.


</div></td>
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

    New-OfficeWebAppsMachine -MachineToJoin server1.contoso.com

이 예제에서는 server1.contoso.com 서버에서 실행되는 Office Web Apps 서버 팜에 현재 서버를 추가합니다.

## 참고 항목


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[인프라 배포: Office Web Apps 서버](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

