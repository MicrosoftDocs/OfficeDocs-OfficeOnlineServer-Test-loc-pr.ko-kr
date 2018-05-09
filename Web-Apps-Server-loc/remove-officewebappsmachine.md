---
title: Remove-OfficeWebAppsMachine
TOCTitle: Remove-OfficeWebAppsMachine
ms:assetid: 5ad806f2-67c6-41ed-a708-69db800f492a
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219440(v=office.15)
ms:contentKeyID: 49643376
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsMachine

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2015-03-09_

Office Web Apps 서버 팜에서 현재 서버를 제거합니다.

## 구문

    Remove-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Remove-OfficeWebAppsMachine** cmdlet은 Office Web Apps 서버 팜에서 현재 서버를 제거합니다. 또한 이 프로세스의 일부분으로 웹 응용 프로그램을 제거하고 Office Web Apps 서버 관련 서비스를 종료합니다. 제거할 서버에서 **Remove-OfficeWebAppsMachine** cmdlet을 실행할 수 없는 경우 Office Web Apps 팜에 있는 다른 서버에서 **Repair-OfficeWebAppsFarm** cmdlet을 사용합니다.


> [!NOTE]
> 로컬 서버가 Office Web Apps 서버 팜의 마스터 서버로 지정되어 있는 경우에는 <STRONG>Set-OfficeWebAppsMachine</STRONG> cmdlet을 사용하여 다른 서버를 마스터로 지정하거나 팜의 다른 서버를 모두 제거해야 해당 서버를 팜에서 제거할 수 있습니다.



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

    Remove-OfficeWebAppsMachine

이 예제에서는 Office Web Apps 서버 팜에서 현재 서버를 제거합니다.

## 참고 항목


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[인프라 배포: Office Web Apps 서버](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

