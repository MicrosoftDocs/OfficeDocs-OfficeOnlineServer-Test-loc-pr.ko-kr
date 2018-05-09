---
title: Windows PowerShell을 사용하여 SharePoint 2013 관리
TOCTitle: Windows PowerShell을 사용하여 SharePoint 2013 관리
ms:assetid: ae4901b4-505a-42a9-b8d4-fca778abc12e
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Ee806878(v=office.15)
ms:contentKeyID: 49643416
ms.date: 03/01/2018
mtps_version: v=office.15
ms.translationtype: MT
---

# Windows PowerShell을 사용하여 SharePoint 2013 관리

 

_**적용 대상:**SharePoint Foundation 2013, SharePoint Server 2013 Enterprise, SharePoint Server 2013 Standard_

_**마지막으로 수정된 항목:**2016-12-16_

**요약:**기본적인 Windows PowerShell cmdlet 및 개념과 SharePoint 2013에서 Windows PowerShell을 사용하는 방법을 설명합니다.

이 문서의 내용

  - 개요

  - SharePoint 2013 제품에서 Windows PowerShell에 액세스

  - 사용 권한

  - 스크립트 및 실행 정책

  - Windows PowerShell 학습

## 개요

Windows PowerShell은 관리자에게 해당하는 API(응용 프로그래밍 인터페이스)에 대한 모든 액세스 권한을 제공하는 명령줄 셸 및 스크립팅 언어입니다. 관리자는 SharePoint 2013와 직접 상호 작용하여 웹 응용 프로그램, 사이트 모음, 사이트, 목록 등을 조작할 수 있으며 cmdlet 스크립트도 작성할 수 있습니다.

Windows PowerShell 3.0은 SharePoint 2013 설치를 위한 필수 구성 요소입니다. Microsoft SharePoint 제품 준비 도구를 실행하면 PowerShell이 아직 설치되지 않은 경우 설치됩니다. Windows PowerShell의 기본 경로는 \<%시스템 루트%\>\\System32\\WindowsPowerShell\\v1.0\\PowerShell.exe입니다.

Windows PowerShell 3.0의 새로운 기능 목록은 [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/p/?linkid=272782)을 참조하세요.

Windows PowerShell 구문에 대해 알아보는 데 도움이 되는 대화형 도구 및 가이드는 [Windows PowerShell 명령 작성기 도구](http://go.microsoft.com/fwlink/p/?linkid=229854) 및 [사용 설명서](http://www.microsoft.com/download/en/details.aspx?id=27588)를 참조하세요.

명령줄 관리 작업을 수행하는 경우 Windows PowerShell을 사용하는 것이 좋습니다. Stsadm 명령줄 도구는 더 이상 사용되지 않지만 이전 제품 버전과의 호환성을 지원하기 위해 포함됩니다.

## SharePoint 2013용 Windows PowerShell 액세스

SharePoint 2013를 설치하고 나면 해당하는 Windows PowerShell cmdlet을 SharePoint 2013 관리 셸에서 사용할 수 있습니다. SharePoint 관리 셸에서는 대부분의 SharePoint 2013 요소를 관리할 수 있습니다. 새 사이트 모음, 웹 응용 프로그램, 사용자 계정, 서비스 응용 프로그램, 프록시 등을 만들 수 있습니다. SharePoint 관리 셸에 명령을 입력하면 Microsoft .NET Framework 기반 SharePoint 개체가 반환됩니다. 이러한 개체를 이후 실행하는 명령의 입력으로 적용하거나 나중에 사용하기 위해 로컬 변수에 저장할 수 있습니다.

SharePoint 관리 셸을 사용하면 cmdlet을 포함하는 스냅인을 등록하지 않아도 됩니다. SharePoint 2013에 대한 Microsoft.SharePoint.PowerShell.dll 모듈 등록은 *%CommonProgramFiles%*\\Microsoft Shared\\Web Server Extensions\\15\\Config\\PowerShell\\Registration에 있는 SharePoint.ps1 파일에서 `Add-PSSnapin Microsoft.SharePoint.PowerShell` 행을 통해 자동으로 수행됩니다. Windows PowerShell 콘솔을 사용하려면 이 스냅인을 수동으로 등록해야 합니다.

SharePoint 관리 셸 또는 Windows PowerShell 콘솔 중 어느 쪽을 사용하든 추가 스냅인을 로드할 수도 있습니다. 자세한 내용은 [프로필 사용자 지정](http://go.microsoft.com/fwlink/p/?linkid=183166)을 참조하세요.

SharePoint 관리 셸에 액세스하려면

1.  SharePoint 관리 셸을 시작합니다.
    
      - Windows Server 2008 R2의 경우:
        
          - **시작**, **Microsoft SharePoint 2013 제품**, **SharePoint 관리 셸**을 차례로 클릭합니다.
    
      - Windows Server 2012의 경우:
        
          - **시작** 화면에서 **SharePoint 관리 셸**을 클릭합니다.
            
            **SharePoint 관리 셸** 이 **시작** 화면에 없는 경우:
        
        <!-- end list -->
        
          - **컴퓨터**를 마우스 오른쪽 단추로 클릭하고 **모든 앱**을 클릭한 다음 **SharePoint 관리 셸**를 클릭합니다.
    
    Windows Server 2012과(와) 상호 작용하는 방법에 대한 자세한 내용은 [Windows Server 2012의 일반 관리 작업 및 탐색](http://technet.microsoft.com/ko-kr/library/hh831491.aspx)을 참조하세요.


> [!NOTE]
> SharePoint 2013 관리 셸과 Windows PowerShell 콘솔에서는 스레딩 모델 사용 방법을 정의하는 <CODE>ReuseThread</CODE> 옵션도 서로 다른 방식으로 사용합니다. SharePoint 2013 관리 셸의 경우 SharePoint.ps1 파일에 있는 <CODE>{Host.Runspace.ThreadOptions = "ReuseThread"}</CODE> 행에서 옵션 사용 방법이 정의됩니다. 자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=183145">PS 스레드 옵션</A>을 참조하세요.



## 사용 권한

## 온-프레미스

**Add-SPShellAdmin**을 사용하여 SharePoint 2013 cmdlet 실행 권한을 사용자에게 부여하려면 다음의 최소 요구 사항을 모두 충족하는지 확인하십시오.

  - SQL Server 인스턴스에 대한 **securityadmin** 고정 서버 역할 멤버 자격이 있어야 합니다.

  - 업데이트하려는 모든 데이터베이스에 대한 **db\_owner** 고정 데이터베이스 역할의 멤버 자격이 있어야 합니다.

  - Windows PowerShell cmdlet을 실행할 서버의 Administrators 그룹 구성원이어야 합니다.


> [!NOTE]
> 이러한 사용 권한이 없는 경우 설치 관리자 또는 SQL Server 관리자에게 문의하여 해당 사용 권한을 요청하십시오.



Windows PowerShell 사용 권한에 대한 자세한 내용은 사용 권한 및 [Add-SPShellAdmin](https://technet.microsoft.com/ko-kr/library/ff607596\(v=office.15\))을 참조하십시오.

**SharePoint\_Shell\_Access** 역할 또는 **WSS\_Admin\_WPG** 로컬 그룹의 구성원이 아닌 경우 **Add-SPShellAdmin** cmdlet을 사용하여 **SharePoint\_Shell\_Access** 역할 및 SharePoint 팜의 모든 프런트 엔드 웹 서버에 **WSS\_Admin\_WPG** 그룹을 추가합니다. SQL Server 데이터베이스에 **SharePoint\_Shell\_Access** 역할이 없으면 **Add-SPShellAdmin** cmdlet 실행 시 해당 역할이 자동으로 만들어집니다. **Add-SPShellAdmin** cmdlet을 실행하고 나면 사용자가 다중 서버 팜 환경에서 SharePoint Windows PowerShell cmdlet을 실행할 수 있습니다.


> [!NOTE]
> SharePoint 2013를 설치하면 설치를 실행하는 사용자 계정에 Windows PowerShell cmdlet 실행을 위한 적절한 권한이 부여됩니다. 사용자가 Windows PowerShell cmdlet을 실행하도록 추가되지 않은 경우 <STRONG>Add-SPShellAdmi</STRONG> cmdlet을 사용하여 사용자를 추가할 수 있습니다.



액세스 권한을 부여하려는 모든 데이터베이스에 대해 **Add-SPShellAdmin** cmdlet을 실행해야 합니다. 데이터베이스를 지정하지 않으면 팜 구성 데이터베이스가 사용됩니다. 데이터베이스를 지정하는 경우에는 지정한 팜 구성 데이터베이스와 함께 팜 콘텐츠 데이터베이스도 포함됩니다.

모든 **SPShellAdmin** cmdlet 목록을 보려면 Windows PowerShell 명령 프롬프트에 `Get-Command -Noun SPShellAdmin`을 입력합니다.

## SharePoint Online

다음 관리 권한이 있는지 확인합니다.

  - Windows PowerShell cmdlet을 실행하는 SharePoint Online 사이트에 대한 전역 관리자 역할을 할당받아야 합니다. 자세한 내용은 [기본 관리 역할 및 사용자 그룹](http://go.microsoft.com/fwlink/p/?linkid=242451)을 참조하세요.
    

    > [!IMPORTANT]
    > SharePoint Online에서는 특정 Windows PowerShell 그룹을 사용할 수 있습니다. 자세한 내용은 <A href="https://technet.microsoft.com/ko-kr/library/fp161362(v=office.15)">SharePoint Online 용 office 365 PowerShell</A>을 참조하십시오.



## 스크립트 및 실행 정책

Windows PowerShell을 사용하여 단일 관리 작업을 수행할 수도 있지만, 스크립트를 사용하면 일련의 작업을 자동화할 수 있습니다. 스크립트는 하나 이상의 Windows PowerShell 명령을 포함하는 텍스트 파일입니다. Windows PowerShell 스크립트의 파일 이름 확장명은 .ps1입니다.

스크립트를 실행하는 데 필요한 SharePoint 2013용 최소 실행 정책은 RemoteSigned입니다(Windows PowerShell용 기본 정책은 Restricted임). 정책을 Restricted로 유지하면 SharePoint 2013 관리 셸에서 Windows PowerShell용 정책을 RemoteSigned로 변경합니다. 즉, **관리자 권한으로 실행**을 선택하여 높은 수준의 관리 권한으로 SharePoint 2013 관리 셸을 시작해야 합니다. 이 변경 내용은 모든 Windows PowerShell 세션에 적용됩니다. 자세한 내용은 [ExecutionPolicy 열거](http://go.microsoft.com/fwlink/p/?linkid=242452)를 참조하세요.

스크립트 및 실행 정책에 대한 자세한 내용은 각각 [about\_scripts](http://go.microsoft.com/fwlink/p/?linkid=144310) 및 [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050)를 참조하세요.

## Windows PowerShell 학습

SharePoint IT 전문가용으로 다양한 Windows PowerShell 학습 리소스가 제공됩니다.

**TechNet Scripting Center**

TechNet Scripting Center는 Windows PowerShell에 대한 기본적인 사항을 학습할 수 있는 많은 리소스를 포함합니다. 또한 여러 Microsoft 제품에서 일반적으로 사용되는 스크립트 예제를 포함하는 스크립트 저장소도 제공합니다. 다음 표에서는 주요 학습 리소스를 보여 줍니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>페이지</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187813">TechNet의 Windows PowerShell 설명서</a></p></td>
<td><p>TechNet 라이브러리의 이 섹션에는 핵심 Windows PowerShell 도움말 항목의 웹 복사본이 포함되어 있습니다. 또한 Windows PowerShell 시작 문서, PowerShell.exe 도움말 및 Windows PowerShell 입문서에 대한 웹 복사본도 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187815">Windows PowerShell을 사용한 스크립팅</a></p></td>
<td><p>Windows PowerShell 스크립팅 학습 리소스의 홈 페이지입니다.</p></td>
</tr>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187817">Windows PowerShell 소유자 설명서</a></p></td>
<td><p>Windows PowerShell을 처음 사용하는 사용자를 위한 웹 기반 가이드입니다.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187819">Windows PowerShell 빠른 참조</a></p></td>
<td><p>Windows PowerShell과 함께 설치되는 빠른 참조 문서의 다운로드 가능한 복사본입니다.</p></td>
</tr>
</tbody>
</table>


이러한 리소스의 내용을 확인할 때는 SharePoint 2013에서 Windows PowerShell을 사용하기 전에 다음과 같은 개념 및 cmdlet에 대해 알아 두면 도움이 됩니다.

  - [Get-Command](http://go.microsoft.com/fwlink/p/?linkid=171069)

  - [Get-Member](http://go.microsoft.com/fwlink/p/?linkid=171070)

  - [Get-Help](http://go.microsoft.com/fwlink/p/?linkid=171068)

  - [별칭 지정](http://go.microsoft.com/fwlink/p/?linkid=113207)

  - [Windows PowerShell의 파이핑 및 파이프라인](http://go.microsoft.com/fwlink/p/?linkid=187808)

  - [cmdlet 매개 변수 집합](http://go.microsoft.com/fwlink/p/?linkid=187810)

  - [Foreach-Object](http://go.microsoft.com/fwlink/p/?linkid=187812)

  - [Where-Object](http://go.microsoft.com/fwlink/p/?linkid=187811)

