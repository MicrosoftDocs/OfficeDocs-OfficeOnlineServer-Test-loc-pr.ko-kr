---
title: Get-OfficeWebAppsFarm
TOCTitle: Get-OfficeWebAppsFarm
ms:assetid: 1f0704e1-a41d-40e6-a31b-08b1926ce811
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219434(v=office.15)
ms:contentKeyID: 49643361
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsFarm

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2013-12-18_

현재 서버가 구성원인 OfficeWebAppsFarm 개체에 대한 세부 정보를 반환합니다.

## 구문

    Get-OfficeWebAppsFarm

## 자세한 설명

**Get-OfficeWebAppsFarm** cmdlet은 현재 서버가 구성원인 OfficeWebAppsFarm 개체에 대한 세부 정보를 반환합니다. 이 개체는 한 단위로 작동하여 Office 문서의 웹 기반 편집 및 보기 기능을 제공하는 서버 그룹을 나타냅니다. **Get-OfficeWebAppsFarm** cmdlet에는 매개 변수가 사용되지 않습니다.

## 매개 변수

## 입력 형식

## 반환 형식

## 예제

\---------------예제 1---------------

    Get-OfficeWebAppsFarm

이 예제에서는 OfficeWebAppsFarm 개체에 대한 세부 정보를 반환합니다.

\---------------예제 2---------------

    (Get-OfficeWebAppsFarm).Machines

이 예제에서는 Office Web Apps 서버 팜의 구성원인 서버에 대한 세부 정보를 반환합니다. 이러한 세부 정보로는 각 서버가 보유한 역할 및 상태가 포함됩니다.

## 참고 항목


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[인프라 배포: Office Web Apps 서버](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

