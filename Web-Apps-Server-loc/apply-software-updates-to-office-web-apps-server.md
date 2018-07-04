---
title: Office Web Apps 서버에 소프트웨어 업데이트 적용
TOCTitle: Office Web Apps 서버에 소프트웨어 업데이트 적용
ms:assetid: 5d15dbd9-374e-422a-a870-43270dd0a2db
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ966220(v=office.15)
ms:contentKeyID: 51658427
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Office Web Apps 서버에 소프트웨어 업데이트 적용

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2016-12-16_

**요약:** Office Web Apps 서버 팜에 소프트웨어 업데이트를 적용하는 방법에 대해 설명합니다.

**대상:** IT 전문가

Office Web Apps 서버가 새로 출시된 후 Microsoft에서는 서버 보안, 성능 및 안정성을 향상시킬 수 있는 일련의 소프트웨어 업데이트를 제공하고 있습니다. 이 문서에서는 Office Web Apps 서버 팜의 개별 서버에 소프트웨어 업데이트를 적용하는 방법을 설명합니다.


> [!IMPORTANT]
> 이 문서는 <A href="content-roadmap-for-office-web-apps-server.md">Office Web Apps 서버의 콘텐츠 로드맵</A>의 일부입니다. 이 로드맵을 Office Web Apps 서버 배포 및 관리를 위한 문서, 다운로드 및 비디오의 시작 지점으로 활용하세요.<BR><STRONG>데스크톱 또는 모바일 장치에서 Office Web Apps 도움말을 찾으십니까?</STRONG> <A href="http://go.microsoft.com/fwlink/p/?linkid=324961">Office.com</A>에서 "Office Web Apps"로 검색하면 필요한 정보를 확인하실 수 있습니다.



<table>
<thead>
<tr class="header">
<th><img src="images/JJ966220.warning(Office.15).gif" title="경고" alt="경고" /><strong>경고:</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>자동 업데이트 프로세스를 통해 Office Web Apps 서버 업데이트를 적용하는 것은 Office Web Apps 서버에서 지원되지 않습니다. Office Web Apps 서버의 업데이트는 이 문서에 설명된 대로 특정 방식으로 적용해야 하기 때문입니다. Office Web Apps 서버 업데이트를 자동으로 적용하면 사용자가 Office Web Apps에서 문서를 보거나 편집하지 못할 수 있습니다. 이 경우 Office Web Apps 서버 팜을 다시 구성해야 합니다. 팜을 다시 구성하려면 <a href="https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps">Remove-OfficeWebAppsMachine</a>을 사용하여 팜에서 Office Web Apps 서버를 제거하고 프로그램 추가/제거를 사용하여 Office Web Apps 서버를 제거한 다음 <a href="deploy-office-web-apps-server.md">Office Web Apps 서버 배포</a>에 설명된 단계에 따라 Office Web Apps 서버를 제거해야 합니다. 다시 설치할 후에는 이 문서에 설명된 단계에 따라 업데이트를 적용합니다.<br />
<a href="plan-office-web-apps-server.md">Office Web Apps Server 업데이트 계획</a>의 지침을 검토하고 Office Web Apps 서버 팜에 대한 업데이트 프로세스를 설정해야 합니다.</td>
</tr>
</tbody>
</table>


## 시작하기 전에

Office Web Apps 서버의 가장 최근 업데이트 목록은 [Microsoft Office 업데이트 블로그](http://go.microsoft.com/fwlink/p/?linkid=280269)및 [Office, Office 서버 및 관련 제품에 대한 TechNet 업데이트 센터](http://go.microsoft.com/fwlink/p/?linkid=280271)에서 확인할 수 있습니다.

Office Web Apps 서버용으로 출시되는 업데이트는 Office Web Apps 서버뿐 아니라 설치된 모든 Office Web Apps 서버 언어 팩을 업데이트합니다. Office Web Apps 서버 언어 팩에 대한 별도의 업데이트는 없습니다.

업데이트 프로세스의 일부로 Office Web Apps 서버 팜을 다시 만들어야 합니다. Office Web Apps 서버 팜을 다시 만들기 위해 준비하려면 Windows PowerShell cmdlet **Get-OfficeWebAppsFarm**을 실행하여 현재 Office Web Apps 서버 팜 속성을 검토하고 [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)에 대한 매개 변수를 검토해야 합니다. **New-OfficeWebAppsFarm**에 사용할 매개 변수는 Office Web Apps 서버 팜을 처음 설치할 때 사용한 매개 변수와 같아야 합니다.


> [!NOTE]
> 마우스, 바로 가기 키 또는 터치를 통해 이 문서에서 설명하는 작업을 완료할 수 있습니다. 자세한 내용은 다음 리소스를 참조하십시오. 
> <UL>
> <LI>
> <P><A href="http://go.microsoft.com/fwlink/p/?linkid=249150">바로 가기 키</A></P>
> <LI>
> <P><A href="http://go.microsoft.com/fwlink/p/?linkid=249151">터치</A></P></LI></UL>



## 단일 서버 Office Web Apps 서버 팜에 소프트웨어 업데이트 적용

단일 서버 Office Web Apps 서버 팜에 소프트웨어 업데이트를 적용하려면 팜에서 Office Web Apps 서버를 제거하고 소프트웨어 업데이트를 적용한 다음 Office Web Apps 서버 팜을 다시 만듭니다. Office Web Apps 서버 팜에 서버가 하나만 있는 경우에는 서버를 업데이트하는 동안 사용자가 Office Web Apps를 사용할 수 없으므로 중요하지 않은 업무 시간 또는 업무 시간이 아닌 시간에 Office Web Apps 서버를 업데이트하는 것이 좋습니다.

**단일 서버 팜에 소프트웨어 업데이트를 적용하려면**

1.  업데이트를 Office Web Apps 서버에 아직 다운로드하지 않은 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?linkid=280274)에서 적용할 Office Web Apps 서버 업데이트를 다운로드합니다.

2.  소프트웨어 업데이트를 적용할 Office Web Apps 서버에서 관리자 권한으로 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.
    
        Remove-OfficeWebAppsMachine

3.  이 서버에 Office Web Apps 서버 업데이트를 설치합니다. 메시지가 나타나면 서버를 다시 시작합니다.

4.  관리자 권한으로 Windows PowerShell 프롬프트를 열고 **New-OfficeWebAppsFarm** cmdlet을 실행하여 Office Web Apps 서버 팜을 다시 만듭니다. **–InternalURL**에 대해 지정한 URL은 Office Web Apps 서버를 실행하는 서버의 이름입니다(예: **http://Contoso-WAC**). 이 경우 이전 Office Web Apps 서버 팜에서 사용한 것과 같은 이름을 사용할 수 있습니다. Office Web Apps 서버 팜을 처음 만들 때 사용한 것과 같은 추가 매개 변수를 사용합니다. 예를 들어 **–AllowHttp** 매개 변수는 HTTP를 사용하도록 팜을 구성하고, **–EditingEnabled** 매개 변수는 SharePoint 2013과 함께 사용할 때 Office Web Apps에서 편집을 지원합니다. **–EditingEnabled** 매개 변수는 Lync Server 2013 또는 Exchange Server 2013에서 사용되지 않습니다. 이러한 호스트는 편집을 지원하지 않기 때문입니다.
    
    다음 예제의 코드는 http://Contoso-WAC라는 새 Office Web Apps 서버 팜을 만듭니다.
    
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    
    변환 서비스, 프록시 서버, 클립 아트 지원 및 온라인 뷰어를 구성하는 추가 매개 변수에 대한 설명은 [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)에 나와 있습니다.

## 여러 Office Web Apps 서버 팜에 소프트웨어 업데이트 적용

여러 Office Web Apps 서버 팜에 소프트웨어 업데이트를 적용하려면 먼저 부하 분산 장치 풀 및 팜에서 서버 중 하나를 제거하고 소프트웨어 업데이트를 적용한 다음 업데이트된 Office Web Apps 서버 팜을 만듭니다. 그런 다음 Office Web Apps 서버 팜에 남아 있는 서버를 제거하고 업데이트하여 업데이트된 새 팜에 가입합니다. 새 팜에 현재 트래픽을 지원할 충분한 서버가 있는 경우 트래픽 부하를 새 팜에 분산시킵니다. 이 업데이트 프로세스를 사용하면 사용자가 중단 없이 Office Web Apps에서 문서를 열고 편집할 수 있습니다.

**여러 서버 팜에 소프트웨어 업데이트를 적용하려면**

1.  [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?linkid=280274)에서 적용할 Office Web Apps 서버 업데이트를 Office Web Apps 서버 팜에 사용할 수 있는 네트워크 위치에 다운로드합니다.

2.  부하 분산 장치 풀에서 소프트웨어 업데이트를 적용할 Office Web Apps 서버를 제거합니다.

3.  해당 Office Web Apps 서버에서 관리자 권한으로 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.
    
        Remove-OfficeWebAppsMachine

4.  이 서버에 Office Web Apps 서버 업데이트를 설치합니다. 메시지가 나타나면 서버를 다시 시작합니다.

5.  관리자 권한으로 Windows PowerShell 프롬프트를 열고 **New-OfficeWebAppsFarm** cmdlet을 사용하여 업데이트된 Office Web Apps 서버 팜을 만듭니다. **–InternalURL**에 대해 지정한 URL은 Office Web Apps 서버를 실행하는 서버의 이름입니다(예: **http://Contoso-WAC**). 이 경우 이전 Office Web Apps 서버 팜에서 사용한 것과 같은 이름을 사용할 수 있습니다. Office Web Apps 서버 팜을 처음 만들 때 사용한 것과 같은 추가 매개 변수를 사용합니다. 예를 들어 **–AllowHttp** 매개 변수는 HTTP를 사용하도록 팜을 구성하고, **–EditingEnabled** 매개 변수는 SharePoint 2013과 함께 사용할 때 Office Web Apps에서 편집을 지원합니다. **–EditingEnabled** 매개 변수는 Lync Server 2013 또는 Exchange Server 2013에서 사용되지 않습니다. 이러한 호스트는 편집을 지원하지 않기 때문입니다.
    
    다음 예제의 코드는 http://Contoso-WAC라는 새 Office Web Apps 서버 팜을 만듭니다.
    
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    
    변환 서비스, 프록시 서버, 클립 아트 지원 및 온라인 뷰어를 구성하는 추가 매개 변수에 대한 설명은 [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)에 나와 있습니다.

6.  Office Web Apps 서버 팜에 있는 서버 수에 따라 트래픽 부하를 새 팜에 분산시킵니다. 더 많은 업데이트된 서버를 팜에 가입할 때까지 이 단계를 지연할 수 있습니다.

7.  팜에 남이 있는 각 서버에 대해 다음 단계를 수행합니다.
    
    1.  부하 분산 장치 풀에서 다음 Office Web Apps 서버를 제거합니다.
    
    2.  이 서버에 Office Web Apps 서버 업데이트를 설치합니다. 메시지가 나타나면 서버를 다시 시작합니다.
    
    3.  관리자 권한으로 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다. **–MachineToJoin** 매개 변수는 현재 서버를 기존 Office Web Apps 서버 팜에 추가합니다. 이 경우 업데이트된 Office Web Apps 서버 팜에 서버를 추가할 수 있습니다. 따라서 업데이트된 Office Web Apps 서버 팜에 있는 서버 중 하나의 컴퓨터 이름을 사용합니다.
        
            New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"

## 참고 항목


[Remove-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[Get-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappsfarm?view=officewebapps-ps)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
  

[](content-roadmap-for-office-web-apps-server.md)

