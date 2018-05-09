---
title: Remove-OfficeWebAppsHost
TOCTitle: Remove-OfficeWebAppsHost
ms:assetid: d0f7b5c2-da0f-421a-8478-c39b247c3ac5
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219453(v=office.15)
ms:contentKeyID: 49643435
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsHost

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2015-03-09_

Office Web Apps 서버 팜의 허용 목록에서 호스트 도메인을 제거합니다.

## 구문

    Remove-OfficeWebAppsHost -Domain <String>

## 자세한 정보

**Remove-OfficeWebAppsHost** cmdlet은 지정한 호스트 도메인을 허용 목록에서 제거합니다. 허용 목록에는 Office Web Apps 서버에서 파일 작업 요청을 허용하는 호스트 도메인이 포함되어 있습니다.


> [!WARNING]
> 허용 목록에 도메인이 없으면 Office Web Apps 서버에서는 모든 도메인의 호스트에 대한 파일 요청을 허용합니다. Office Web Apps 서버 팜을 인터넷에서 액세스할 수 있는 경우에는 이 목록을 비워 두지 마십시오. 목록을 비워 두면 모든 사용자가 Office Web Apps 서버 팜을 사용하여 콘텐츠를 보고 편집할 수 있습니다.



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
<th>유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Domain</strong></p></td>
<td><p>필수</p></td>
<td><p>System.String</p></td>
<td><p>허용 목록에서 제거할 호스트 도메인을 지정합니다.</p></td>
</tr>
</tbody>
</table>


## 입력 형식

## 반환 형식

## 예제

\---------------예제 1---------------

    Remove-OfficeWebAppsHost -domain "contoso.com"

이 예제에서는 허용 목록에서 contoso.com 도메인을 제거합니다.

## 참고 항목


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Get-OfficeWebAppsHost](get-officewebappshost.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[인프라 배포: Office Web Apps 서버](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

