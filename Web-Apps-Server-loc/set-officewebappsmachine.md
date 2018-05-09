---
title: Set-OfficeWebAppsMachine
TOCTitle: Set-OfficeWebAppsMachine
ms:assetid: aeba2638-be88-4030-80fe-7e4bcd30309b
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219448(v=office.15)
ms:contentKeyID: 49643421
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsMachine

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2015-03-09_

Office Web Apps 서버 팜에 있는 현재 서버의 설정을 변경합니다.

## 구문

    Set-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-Master <String>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Set-OfficeWebAppsMachine** cmdlet은 Office Web Apps 서버 팜에 있는 현재 서버의 설정을 변경합니다. 이러한 설정으로는 현재 서버가 보유한 역할과 팜에 대해 지정된 마스터 서버가 포함됩니다.

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
<td><p><strong>Confirm</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Master</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p></p>
<p>마스터 팜 구성 파일을 저장하는 서버를 지정합니다.</p>
<p>로컬 서버를 마스터로 설정하는 경우에는 Office Web Apps 서버 팜의 나머지 서버에서 모두 <strong>Set-OfficeWebAppsMachine -Master</strong>를 실행하여 해당 서버가 새 마스터를 가리키도록 해야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roles</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String[]</p></td>
<td><p>로컬 서버에 할당할 서버 역할 목록을 쉼표로 구분하여 지정합니다.</p>
<p>역할 유형은 다음과 같습니다.</p>
<p><strong>All</strong></p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">

> [!IMPORTANT]
> Office Web Apps 서버 팜의 모든 서버에서 모든 역할을 실행하는 것이 가장 좋습니다. Office Web Apps 서버 팜에 서버가 50개 정도 포함되어야 역할 할당을 통한 이점을 얻을 수 있습니다.


</div></td>
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

    (Get-OfficeWebAppsFarm).Machines

이 예제에서는 Office Web Apps 서버 팜의 각 서버가 보유한 역할을 표시합니다.

\---------------예제 2---------------

    Set-OfficeWebAppsMachine -Roles FrontEnd

이 예제에서는 현재 서버를 프런트 엔드 서버로 구성합니다.

\---------------예제 3---------------

    Set-OfficeWebAppsMachine -Roles All

이 예제에서는 현재 서버가 모든 역할을 호스팅하도록 구성합니다.

## 참고 항목


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[인프라 배포: Office Web Apps 서버](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

