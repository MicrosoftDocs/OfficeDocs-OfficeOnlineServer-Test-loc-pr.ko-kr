---
title: Repair-OfficeWebAppsFarm
TOCTitle: Repair-OfficeWebAppsFarm
ms:assetid: 083d8e25-ce82-4884-9bbc-06375185011c
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219433(v=office.15)
ms:contentKeyID: 49643360
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Repair-OfficeWebAppsFarm

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2015-03-09_

비정상으로 플래그가 지정된 모든 서버를 Office Web Apps 서버 팜에서 제거합니다.

## 구문

    Repair-OfficeWebAppsFarm [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Repair-OfficeWebAppsFarm** cmdlet은 비정상으로 플래그가 지정된 모든 서버를 Office Web Apps 서버 팜에서 제거합니다. 이 cmdlet은 팜 토폴로지를 업데이트하지만 제거되는 서버의 웹 응용 프로그램 및 서비스를 정리하지는 않습니다. 따라서 가능하면 비정상 상태의 서버에서 **Remove-OfficeWebAppsMachine** cmdlet을 실행하여 팜에서 해당 서버를 완전하게 제거하는 것이 좋습니다. 비정상 상태의 서버에서 오류가 발생하여 **Remove-OfficeWebAppsMachine** cmdlet을 해당 서버에 대해 직접 실행할 수 없는 경우에만 **Repair-OfficeWebAppsFarm** cmdlet을 사용하십시오.

비정상 상태의 서버가 여러 개이면 각 서버를 제거하기 전에 메시지가 표시됩니다. 비정상 상태의 서버가 없으면 이 cmdlet은 아무런 작업도 수행하지 않습니다.

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
<th>종류</th>
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
<td><p><strong>Force</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>사용자 프롬프트에 대한 모든 대답이 예라고 가정합니다.</p></td>
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

    (Get-OfficeWebAppsFarm).Machines

이 예제에서는 Office Web Apps 서버 팜에 있는 모든 서버의 상태를 표시합니다.

\---------------예제 2---------------

    Repair-OfficeWebAppsFarm

이 예제에서는 비정상 상태의 모든 서버를 Office Web Apps 서버 팜에서 제거합니다.

## 참고 항목


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[인프라 배포: Office Web Apps 서버](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

