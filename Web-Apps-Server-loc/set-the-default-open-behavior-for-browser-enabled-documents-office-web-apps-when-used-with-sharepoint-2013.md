---
title: 브라우저 지원 문서에 대한 기본 열기 동작 설정(Office Web Apps를 SharePoint 2013과 함께 사용하는 경우)
TOCTitle: 브라우저 지원 문서에 대한 기본 열기 동작 설정
ms:assetid: e27e0bc8-5fb5-4bb1-8157-d7c90654175e
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Ee837425(v=office.15)
ms:contentKeyID: 50181193
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# 브라우저 지원 문서에 대한 기본 열기 동작 설정(Office Web Apps를 SharePoint 2013과 함께 사용하는 경우) 

_**적용 대상:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**마지막으로 수정된 항목:** 2016-12-16_

**요약:** SharePoint 사이트 모음 및 문서 라이브러리에서 Office 문서의 기본 열기 동작을 구성하는 방법에 대해 설명합니다.

**대상:** IT 전문가

SharePoint 2013 문서 라이브러리에서 문서를 열려면 문서 제목을 클릭하기만 하면 됩니다. 다음에 발생하는 상황(파일이 클라이언트 응용 프로그램에서 열리는지, 브라우저에 열리는지)은 파일 형식, Office Web Apps 서버 팜을 설정한 방법, 라이브러리 또는 사이트 모음의 OpenInClient 기능 설정을 지정한 방법 등 여러 가지 요소에 따라 달라집니다. 다음 단계에는 Office Web Apps 서버를 사용하도록 SharePoint 2013을 구성한 경우 Office 문서의 기본 열기 동작을 구성하는 방법이 나와 있습니다.

## SharePoint 2013 라이브러리에서 문서가 열리는 방법 설정

기본적으로 Office Web Apps 서버를 사용하도록 SharePoint 2013을 구성한 경우 Word, PowerPoint, Excel 또는 OneNote 파일을 클릭하면 파일이 브라우저에서 열립니다. PDF 문서는 Word Web App에서 열립니다. 다음 두 가지 방법으로 이 기본 동작을 변경하여 파일이 클라이언트 응용 프로그램(또는 기본 PDF 뷰어)에서 대신 열리도록 할 수 있습니다.

  - **SharePoint 2013 팜의 경우** [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps) 및 [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps)Windows PowerShell cmdlet을 사용하여 SharePoint 2013 팜에 대한 기본 열기 동작을 파일 형식별로 조정할 수 있습니다. 이러한 cmdlet을 사용하여 [PDF 문서의 동작을 조정](http://go.microsoft.com/fwlink/p/?linkid=330246)할 수도 있습니다.

  - **사이트 모음 또는 문서 라이브러리의 경우** 사이트 모음 관리자 및 사용자는 SharePoint 2013의 OpenInClient 기능을 사용하여 Office 파일이 클라이언트 응용 프로그램에서 열리도록 할지, 브라우저에서 열리도록 할지를 지정할 수 있습니다. 사용자는 문서 라이브러리 속성에서 이 설정을 변경할 수 있으며, 사이트 모음 관리자는 사이트 모음 관리에서 또는 [Enable-SPFeature](https://technet.microsoft.com/ko-kr/library/ff607803\(v=office.15\)) cmdlet으로 OpenInClient 기능을 사용하도록 설정함으로써 이 설정을 변경할 수 있습니다. OpenInClient 기능을 사용하도록 설정하는 여러 가지 방법은 다음 섹션을 참조하세요.

일반적으로 OpenInClient 기능은 SharePoint 2013과 Office Web Apps 서버 사이에 설정한 모든 WOPI 바인딩을 무시합니다. 즉 SharePoint 2013 라이브러리 또는 사이트 모음의 OpenInClient 기능을 사용하도록 설정하면 SharePoint 2013 서버가 Office Web Apps 서버를 사용하도록 구성된 경우에도 문서가 클라이언트 응용 프로그램에서 열립니다.


> [!NOTE]
> 브라우저 지원 문서의 기본 열기 동작 구성은 사용자가 SharePoint 2013에서 <STRONG>체크 아웃</STRONG> 및 <STRONG>보내기</STRONG> 기능을 사용하여 문서를 다운로드할 수 있는지에 영향을 주지 않습니다. SharePoint 2013에서 체크 아웃, 다운로드 및 보기 권한을 구성하는 방법에 대한 자세한 내용은 <A href="https://technet.microsoft.com/ko-kr/library/cc262939(v=office.15)">SharePoint 2013에서 사이트 및 콘텐츠에 대한 사용 권한 계획</A>을 참조하세요.



## 문서 라이브러리 또는 사이트 모음에 대한 OpenInClient 기능 설정

SharePoint 2013에서 OpenInClient 기능을 설정하려면 다음 절차 중 하나를 사용합니다.


> [!NOTE]
> 이러한 절차 중 일부에서는 SharePoint 2013 관리 셸을 사용하여 SharePoint cmdlet을 실행합니다. Windows PowerShell 콘솔을 사용하려면 <STRONG>Add-PSSnapin</STRONG> cmdlet을 사용하여 Microsoft.SharePoint.PowerShell 스냅인을 추가해야 합니다. SharePoint 2013에서 Windows PowerShell을 사용하는 방법에 대한 자세한 내용은 <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">Windows PowerShell을 사용하여 SharePoint 2013 관리</A>를 참조하세요.


> [!NOTE]
> Office 2013 제품군의 작업은 마우스, 바로 가기 키 또는 터치를 사용하여 완료할 수 있습니다. Office 제품 및 서비스에서 바로 가기 키와 터치를 사용하는 방법에 대한 자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=249150">바로 가기 키</A> 및 <A href="http://go.microsoft.com/fwlink/p/?linkid=253163">Office 터치 가이드</A>를 참조하세요.

 **사이트 모음에 대한 OpenInClient 기능 설정**

1.  SharePoint 사이트 모음에서 **설정** 아이콘 \> **사이트 설정**을 선택합니다.

2.  **사이트 설정** 페이지의 **사이트 모음 관리**에서 **사이트 모음 기능**을 선택합니다.

3.  **기능** 페이지의 **기본적으로 클라이언트 응용 프로그램에서 문서 열기** 기능에서 문서를 클라이언트 응용 프로그램에서 열려면 **활성화**(OpenInClient 기능 사용)를 선택하고 문서를 브라우저에서 열려면 **비활성화**(OpenInClient 기능 사용 안 함)를 선택합니다.

 **Windows PowerShell을 사용하여 사이트 모음의 기본 열기 동작 설정**

1.  먼저 다음 구성원 자격이 있는지 확인합니다.
    
      - SQL Server 인스턴스에 대한 **securityadmin** 고정 서버 역할
    
      - 업데이트하려는 모든 데이터베이스에 대한 **db\_owner** 고정 데이터베이스 역할
    
      - Windows PowerShell cmdlet을 실행 중인 서버의 Administrators 그룹
    
    또한 [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050)를 살펴보고 필요한 다른 구성원 자격을 추가합니다.
    
    관리자는 **Add-SPShellAdmin** cmdlet을 사용하여 SharePoint 2013 cmdlet 사용 권한을 부여할 수 있습니다.
    

    > [!NOTE]
    > 사용 권한이 없는 경우에는 설치 관리자 또는 SQL Server 관리자에게 문의하여 요청하도록 합니다. Windows PowerShell 사용 권한에 대한 자세한 내용은 <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">사용 권한</A> 및 <A href="https://technet.microsoft.com/ko-kr/library/ff607596(v=office.15)">Add-SPShellAdmin</A>을 참조하세요.



2.  관리자 권한으로 SharePoint 2013 관리 셸을 엽니다.
    
    **Windows Server 2008의 경우**
    
    1.  **시작** 메뉴에서 **모든 프로그램**을 선택합니다.
    
    2.  **Microsoft SharePoint 2013 제품**을 선택합니다.
    
    3.  **SharePoint 2013 관리 셸**을 선택하고 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 표시합니다.
    
    4.  바로 가기 메뉴에서 **관리자 권한으로 실행**을 선택합니다.
    
    **Windows Server 2012의 경우**
    
    1.  화면 모서리에서 살짝 밀어 참을 표시한 다음 **검색**을 선택하여 컴퓨터에 설치되어 있는 응용 프로그램을 모두 표시합니다.
    
    2.  **SharePoint 2013 관리 셸**을 선택(마우스 오른쪽 단추로 클릭)하여 앱 바를 표시합니다.
    
    3.  앱 바에서 **관리자 권한으로 실행**을 선택합니다.

3.  Windows PowerShell 명령 프롬프트에서 다음 명령 중 하나를 입력합니다.
    
      - 모든 사이트 모음에 대해 OpenInClient 기능을 사용하도록 설정(브라우저에서 문서 열기)하려면 다음 명령을 입력합니다.
        
        ```PowerShell
            Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
        ```
        ```  
        여기서 *\<SiteCollURL\>*은 사이트 모음의 URL입니다.
        ```
    
      - 모든 사이트 모음에 대해 OpenInClient 기능을 사용하도록 설정(클라이언트 응용 프로그램에서 문서 열기)하려면 다음 명령을 입력합니다.
        
        ```PowerShell
            Get-SPSite -limit ALL |foreach{ Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL }
        ```
    
      - 특정 사이트 모음에 대해 OpenInClient 기능을 사용하지 않도록 설정(브라우저에서 문서 열기)하려면 다음 명령을 입력합니다.
        
        ```PowerShell
            Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
        ```
        ```  
        여기서 *\<SiteCollURL\>*은 사이트 모음의 URL입니다.
        ```
    
      - 모든 사이트 모음에 대해 OpenInClient 기능을 사용하지 않도록 설정(브라우저에서 문서 열기)하려면 다음 명령을 입력합니다.

        ```PowerShell  
            Get-SPSite -limit ALL |foreach{ Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL 
        ``` 

 **문서 라이브러리 설정 페이지를 사용하여 문서 라이브러리의 기본 열기 동작 설정**

1.  문서 라이브러리 페이지에서 **라이브러리** 탭을 선택합니다.

2.  **설정** 그룹에서 **라이브러리 설정**을 선택합니다.

3.  **문서 라이브러리 설정** 페이지에서 **고급 설정**을 선택합니다.

4.  **고급 설정** 페이지의 **브라우저에서 문서 열기**에서 다음 옵션 중 하나를 선택합니다.
    
      - **클라이언트 응용 프로그램에서 열기**   사용자가 이 라이브러리에서 문서를 선택하면 해당 클라이언트 응용 프로그램(사용 가능한 경우)에서 문서가 열립니다.
    
      - **브라우저에서 열기**   사용자가 이 라이브러리에서 문서를 선택하면 웹 브라우저의 해당 문서 유형에 대한 웹 앱에서 문서가 열립니다. 문서가 웹 앱에서 열린 경우 사용자는 클라이언트 응용 프로그램에서 문서를 열지 결정할 수 있습니다.
    
      - **서버 기본값 사용**   사용자가 이 라이브러리에서 문서를 선택하면 SharePoint 2013 실행 서버에 지정된 기본 열기 동작을 사용하여 문서가 열립니다.

 **Windows PowerShell을 사용하여 IRM 보호 문서 라이브러리의 기본 열기 동작 설정**

1.  먼저 다음 구성원 자격이 있는지 확인합니다.
    
      - SQL Server 인스턴스에 대한 **securityadmin** 고정 서버 역할
    
      - 업데이트하려는 모든 데이터베이스에 대한 **db\_owner** 고정 데이터베이스 역할
    
      - Windows PowerShell cmdlet을 실행 중인 서버의 Administrators 그룹
    
    또한 [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050)를 살펴보고 필요한 다른 구성원 자격을 추가합니다.
    
    관리자는 **Add-SPShellAdmin** cmdlet을 사용하여 SharePoint 2013 cmdlet 사용 권한을 부여할 수 있습니다.
    

    > [!NOTE]
    > 사용 권한이 없는 경우에는 설치 관리자 또는 SQL Server 관리자에게 문의하여 요청하도록 합니다. Windows PowerShell 사용 권한에 대한 자세한 내용은 <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">사용 권한</A> 및 <A href="https://technet.microsoft.com/ko-kr/library/ff607596(v=office.15)">Add-SPShellAdmin</A>을 참조하세요.



2.  관리자 권한으로 SharePoint 2013 관리 셸을 엽니다.
    
    **Windows Server 2008의 경우**
    
    1.  **시작** 메뉴에서 **모든 프로그램** 을 선택합니다.
    
    2.  **Microsoft SharePoint 2013 제품** 을 선택합니다.
    
    3.  **SharePoint 2013 관리 셸** 을 선택하고 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 표시합니다.
    
    4.  바로 가기 메뉴에서 **관리자 권한으로 실행** 을 선택합니다.
    
    **Windows Server 2012의 경우**
    
    1.  화면 모서리에서 살짝 밀어 참을 표시한 다음 **검색** 을 선택하여 컴퓨터에 설치되어 있는 응용 프로그램을 모두 표시합니다.
    
    2.  **SharePoint 2013 관리 셸** 을 선택(마우스 오른쪽 단추로 클릭)하여 앱 바를 표시합니다.
    
    3.  앱 바에서 **관리자 권한으로 실행** 을 선택합니다.

3.  Windows PowerShell 명령 프롬프트에서 다음 명령을 입력합니다.
    
      ```PowerShell
        Get-SPWeb -site <SiteCollURL> | % {$_.Lists} | where {$_.IrmEnabled -eq $true} | % {$_.DefaultItemOpen =[Microsoft.Sharepoint.DefaultItemOpen]::<DefaultItemOpenSetting>; $_.Update()}
      ```
    
    여기서 각 부분이 나타내는 의미는 다음과 같습니다.
    
      - *\<SiteCollURL\>*은 문서 라이브러리가 있는 사이트 모음의 URL입니다.
    
      - *\<DefaultItemOpenSetting\>*은 기본 열기 동작을 지정하는 **DefaultItemOpen** 열거형 값입니다. 연결된 클라이언트 응용 프로그램(사용 가능한 경우)에서 문서를 열려면 **PreferClient** 를 사용하고, 브라우저에서 문서를 열려면 **Browser** 를 사용합니다.

## 참고 항목


[Get-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIBinding?view=sharepoint-ps)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[Windows PowerShell을 사용하여 SharePoint 2013 관리](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps)  
[Office Web Apps 서버](office-web-apps-server.md)  


[Get-SPWeb](https://technet.microsoft.com/ko-kr/library/ff607807\(v=office.15\))  
[Get-SPSite](https://technet.microsoft.com/ko-kr/library/ff607950\(v=office.15\))  
[Get-SPFeature](https://technet.microsoft.com/ko-kr/library/ff607945\(v=office.15\))

