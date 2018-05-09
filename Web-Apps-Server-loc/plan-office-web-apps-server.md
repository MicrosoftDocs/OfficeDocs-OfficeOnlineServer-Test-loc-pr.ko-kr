---
title: Office Web Apps 서버 계획
TOCTitle: Office Web Apps 서버 계획
ms:assetid: 2e147f11-6f47-46bc-90bf-b2f179958d11
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219435(v=office.15)
ms:contentKeyID: 49643362
ms.date: 02/08/2018
mtps_version: v=office.15
ms.translationtype: MT
---

# Office Web Apps 서버 계획

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2017-10-10_

**요약:** HTTPS, 인증서, 가상화, 부하 분산, 토폴로지 및 보안 등 Office Web Apps 서버의 요구 사항과 필수 구성 요소에 대해 설명합니다.

**대상:** IT 전문가

Office Web Apps 서버는 온-프레미스 환경에서 브라우저 기반 버전의 Office 앱을 제공함으로써 유연성을 개선하고 공동 작업 기회를 확장합니다. 이 문서에서는 조직에 Office Web Apps 서버를 설치하기 위해 수행해야 하는 단계와 요구 사항을 설명합니다.

SharePoint 2013 및 Lync Server 2013 같은 모든 호스트 Office Web Apps 서버 와 통신할 수 있도록 신중 하 게 계획을 고려해 야 합니다. 호스트를 구성 하는 방법에 대 한 추가 지침은 다음 리소스를 참조 합니다.

  - [SharePoint 2013과 함께 사용되는 Office Web Apps 계획](plan-office-web-apps-used-with-sharepoint-2013.md)

  - [Office Web Apps Server 및 Lync Server 2013 배포](https://go.microsoft.com/fwlink/p/?linkid=256902)


> [!NOTE]
> SharePoint 2010 제품 Office Web Apps 서버 에 대 한 호스트 수 없습니다. Office Web Apps 서버SharePoint Foundation 2010 또는 SharePoint Server 2010 에서 지원 되지 않습니다. 또한 Office Web Apps 서버Exchange Server 2013 에서 지원 되지 않습니다.



이 문서의 내용

  - Office Web Apps 서버의 소프트웨어, 하드웨어 및 구성 요구 사항

  - Office Web Apps 서버 가상화 지원

  - Office Web Apps 서버의 방화벽 요구 사항

  - Office Web Apps 서버의 부하 분산 장치 요구 사항

  - Office Web Apps 서버의 DNS 요구 사항

  - Office Web Apps 서버용 언어 팩 계획

  - Office Web Apps 서버에 대한 토폴로지 계획

  - Office Web Apps 서버 보안 계획

  - Office Web Apps 서버에서 온라인 뷰어 계획

  - Office Web Apps 서버 업데이트 계획

## Office Web Apps 서버의 소프트웨어, 하드웨어 및 구성 요구 사항

Office Web Apps 서버는 단일 서버 Office Web Apps 서버 팜 또는 부하 분산된 다중 서버 Office Web Apps 서버 팜으로 설치할 수 있습니다. 실제 서버 또는 가상 컴퓨터 인스턴스를 사용할 수는 있지만 Office Web Apps 서버와 동일한 서버에 다른 서버 응용 프로그램(예: SharePoint 2013 또는 SQL Server)을 설치할 수는 없습니다.

실제 사용자 데이터가 포함된 환경에서는 항상 HTTPS를 사용하는 것이 좋은데, 이 경우 인증서를 가져와야 합니다. 팜에서 여러 서버를 사용하는 경우에는 하드웨어 또는 소프트웨어 부하 분산 솔루션을 구성해야 합니다. 이러한 시나리오에 대한 자세한 내용은 다음 섹션에서 확인할 수 있습니다.

## Office Web Apps 서버의 하드웨어 요구 사항

Office Web Apps 서버에서 사용되는 최소 하드웨어 요구 사항은 SharePoint Server 2013과 동일합니다. 전체 SharePoint 2013 요구 사항 집합은 [하드웨어 요구 사항 - 웹 서버, 응용 프로그램 서버 및 단일 서버 설치](https://technet.microsoft.com/ko-kr/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver)에서 확인할 수 있습니다.

## Office Web Apps 서버의 지원되는 운영 체제

Office Web Apps 서버는 다음 운영 체제에서 실행할 수 있습니다.

  - 64 비트 버전의 Windows Server 2008 R2 SP1(서비스 팩 1) 표준, 엔터프라이즈 또는 설치 된 [업데이트에 대 한 Windows Server 2008 R2 x64 Edition](https://go.microsoft.com/fwlink/p/?linkid=236954) Datacenter

  - 64비트 버전의 Windows Server 2012 Standard 또는 Datacenter

  - 64비트 버전의 Windows Server 2012 R2. 이 운영 체제를 사용하려면 Office Web Apps 서버 SP1(서비스 팩 1)을 사용해야 합니다.

## Office Web Apps 서버의 도메인 요구 사항

Office Web Apps 서버 팜의 모든 서버는 도메인의 일부여야 합니다. 이러한 서버는 같은 도메인(권장)에 있거나 같은 포리스트의 여러 도메인에 있을 수 있습니다. 그러나 도메인 컨트롤러에 설치하려는 경우에는 Office Web Apps 서버가 작동하지 않습니다.

## Office Web Apps 서버에 필요한 서버 역할, 서비스 및 기타 소프트웨어

먼저 Office Web Apps 서버를 배포할 때 설치하면 안 되는 항목을 알아보겠습니다.

  - **Office Web Apps 서버를 실행하는 서버에 다른 서버 응용 프로그램을 설치하면 안 됨**. 여기에는 Exchange Server, SharePoint Server, Lync Server 및 SQL Server가 포함됩니다. 서버가 부족한 경우 보유한 서버 중 하나의 가상 컴퓨터 인스턴스에서 Office Web Apps 서버를 실행하는 것이 좋습니다.

  - **포트 80, 443 또는 809에서 웹 서버(IIS) 역할을 사용하는 서비스 또는 역할을 설치하면 안 됨**. Office Web Apps 서버는 이러한 포트에서 웹 응용 프로그램을 주기적으로 제거하기 때문입니다.

  - **모든 Office 버전을 설치하면 안 됨**. 이미 설치한 경우에는 Office Web Apps 서버를 설치하기 전에 제거해야 합니다.

  - **도메인 컨트롤러에 Office Web Apps 서버를 설치하면 안 됨**. AD DS(Active Directory 도메인 서비스)가 설치된 서버에서는 실행되지 않습니다.

이제 설치해야 하는 항목을 알아보겠습니다. 자세한 내용은 다음 표를 참조하세요.


> [!IMPORTANT]
> Office Web Apps 서버 은 <A href="https://go.microsoft.com/fwlink/p/?linkid=256561">볼륨 라이선스 서비스 센터 (VLSC)</A>에서 다운로드할 수만 있습니다. Office Web Apps 서버 을 다운로드 하려면 Office Professional Plus 2013, Office Standard 2013 또는 Office for Mac 2011 에 대 한 볼륨 라이선스 계약에 따라는 라이선스가 있어야 합니다. VLSC 포털에서 이러한 Office 제품 다운로드 수 있습니다.



### Office Web Apps 서버에 필요한 다운로드, 서버 역할 및 기능

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>다운로드, 서버 역할 또는 기능</th>
<th>Windows Server 2008 R2를 설치하는 경우</th>
<th>Windows Server 2012를 설치하는 경우</th>
<th>Windows Server 2012 R2에 설치하는 경우</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>다운로드:</strong> Office Web Apps 서버</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Office Web Apps 서버</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Office Web Apps 서버</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Office Web Apps 서버</a></p></td>
</tr>
<tr class="even">
<td><p><strong>다운로드:</strong> Office Web Apps 서버 SP1</p></td>
<td><p>권장</p></td>
<td><p>권장</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510097">Office Web Apps 서버 s p 1</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>다운로드:</strong> 올바른 버전의 .NET Framework</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256560">.NET Framework 4.5</a></p></td>
<td><p>.NET framework 4.5가 이미 설치되어 있음</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510096">.NET Framework 4.5.2</a></p></td>
</tr>
<tr class="even">
<td><p><strong>다운로드:</strong> Windows Server 2008 R2 x64 Edition용 업데이트</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=236954">Windows Server 2008 R2 x64 Edition 용 업데이트</a></p></td>
<td><p>해당 없음</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p><strong>다운로드:</strong> Windows PowerShell 3.0</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=244693">Windows PowerShell 3.0</a></p></td>
<td><p>이미 설치됨</p></td>
<td><p>이미 설치됨</p></td>
</tr>
<tr class="even">
<td><p><strong>서버 역할:</strong> 웹 서버(IIS)</p></td>
<td><p>아래 <strong>웹 서버(IIS)</strong> 서버 역할에 필요한 최소 역할 서비스가 나와 있습니다.</p>
<p><strong>일반 HTTP 기능</strong></p>
<ul>
<li><p>정적 콘텐츠</p></li>
<li><p>기본 문서</p></li>
</ul>
<p><strong>응용 프로그램 개발</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>.NET 확장성</p></li>
<li><p>ISAPI 확장</p></li>
<li><p>ISAPI 필터</p></li>
<li><p>Server Side Includes</p></li>
</ul>
<p><strong>보안</strong></p>
<ul>
<li><p>Windows 인증</p></li>
<li><p>요청 필터링</p></li>
</ul>
<p><strong>관리 도구</strong></p>
<ul>
<li><p>IIS 관리 콘솔</p></li>
</ul>
<p>다음 옵션은 반드시 사용해야 하는 것은 아니지만 사용하는 것이 좋습니다.</p>
<p><strong>성능</strong></p>
<ul>
<li><p>정적 콘텐츠 압축</p></li>
<li><p>동적 콘텐츠 압축</p></li>
</ul></td>
<td><p>아래 <strong>웹 서버(IIS)</strong> 서버 역할에 필요한 최소 역할 서비스가 나와 있습니다.</p>
<p><strong>관리 도구</strong></p>
<ul>
<li><p>IIS 관리 콘솔</p></li>
</ul>
<p><strong>웹 서버</strong></p>
<ul>
<li><p>일반 HTTP 기능</p></li>
<li><p>기본 문서</p></li>
<li><p>정적 콘텐츠</p></li>
</ul>
<p><strong>보안</strong></p>
<ul>
<li><p>요청 필터링</p></li>
<li><p>Windows 인증</p></li>
</ul>
<p><strong>응용 프로그램 개발</strong></p>
<ul>
<li><p>.NET Extensibility 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>ISAPI 확장</p></li>
<li><p>ISAPI 필터</p></li>
<li><p>SSI(Server Side Includes)</p></li>
</ul>
<p>다음 서비스는 반드시 사용해야 하는 것은 아니지만 사용하는 것이 좋습니다.</p>
<p><strong>성능</strong></p>
<ul>
<li><p>정적 콘텐츠 압축</p></li>
<li><p>동적 콘텐츠 압축</p></li>
</ul></td>
<td><p>아래 <strong>웹 서버(IIS)</strong> 서버 역할에 필요한 최소 역할 서비스가 나와 있습니다.</p>
<p><strong>관리 도구</strong></p>
<ul>
<li><p>IIS 관리 콘솔</p></li>
</ul>
<p><strong>웹 서버</strong></p>
<ul>
<li><p>일반 HTTP 기능</p></li>
<li><p>기본 문서</p></li>
<li><p>정적 콘텐츠</p></li>
</ul>
<p><strong>보안</strong></p>
<ul>
<li><p>요청 필터링</p></li>
<li><p>Windows 인증</p></li>
</ul>
<p><strong>응용 프로그램 개발</strong></p>
<ul>
<li><p>.NET Extensibility 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>ISAPI 확장</p></li>
<li><p>ISAPI 필터</p></li>
<li><p>SSI(Server Side Includes)</p></li>
</ul>
<p>다음 서비스는 반드시 사용해야 하는 것은 아니지만 사용하는 것이 좋습니다.</p>
<p><strong>성능</strong></p>
<ul>
<li><p>정적 콘텐츠 압축</p></li>
<li><p>동적 콘텐츠 압축</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>기능:</strong> 잉크 및 필기 서비스</p></td>
<td><p><strong>잉크 및 필기 서비스</strong></p>
<ul>
<li><p>잉크 지원</p></li>
</ul></td>
<td><p><strong>잉크 및 필기 서비스</strong></p>
<ul>
<li><p>잉크 지원은 필요하지 않습니다.</p></li>
</ul></td>
<td><p><strong>잉크 및 필기 서비스</strong></p>
<ul>
<li><p>잉크 지원은 필요하지 않습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Office Web Apps 서버 가상화 지원

Office Web Apps 서버는 Windows ServerHyper-V 기술을 사용하여 배포할 때 완벽하게 지원됩니다. Office Web Apps 서버를 가상화할 계획이라면 다음 지침을 따르세요.

  - 자체 가상 컴퓨터 인스턴스에 Office Web Apps 서버를 설치합니다. 이 인스턴스에는 SharePoint 2013 등의 다른 서버 응용 프로그램을 설치하지 마세요.

  - SharePoint 2013을 실행하는 서버를 통해 호스팅되는 가상 컴퓨터 인스턴스에는 Office Web Apps 서버를 설치할 수 있습니다.

  - 다중 서버 Office Web Apps 서버 팜의 경우 각 인스턴스가 별도의 가상 컴퓨터 호스트에 있어야 호스트 중 하나에 장애가 발생해도 Office Web Apps 서버 팜을 계속 사용할 수 있습니다.

## Office Web Apps 서버의 방화벽 요구 사항

웹 브라우저, Office Web Apps 서버를 실행하는 서버 및 SharePoint 2013을 실행하는 서버 간의 통신을 차단하는 방화벽으로 인한 문제가 발생할 수 있습니다. 서버가 네트워크의 서로 다른 부분에 있는 경우에는 이러한 문제가 더욱 복잡해질 수 있습니다.

Office Web Apps 서버 또는 부하 분산 장치를 실행하는 서버에서 다음 포트가 방화벽에 의해 차단되지 않는지 확인합니다.

  - HTTPS 트래픽용 포트 443

  - HTTP 트래픽용 포트 80

  - Office Web Apps 서버를 실행하는 서버 간의 전용 트래픽용 포트 809(다중 서버 팜을 설정하는 경우)

## Office Web Apps 서버의 부하 분산 장치 요구 사항

둘 이상의 서버에서 Office Web Apps 서버를 실행할 때에는 부하 분산 솔루션을 사용하는 것이 좋습니다. ARR(응용 프로그램 요청 라우팅)을 실행하는 웹 서버(IIS) 역할의 서버를 포함하여 거의 모든 부하 분산 솔루션을 사용할 수 있습니다. 실제로 Office Web Apps 서버를 실행하는 서버 중 하나에서 ARR을 실행할 수 있습니다. 부하 분산 솔루션이 없는 경우에는 ARR과 함께 IIS를 사용하는 방법이 설명된 다음 리소스를 참조하세요.

  - [설치 응용 프로그램 요청 라우팅](https://go.microsoft.com/fwlink/?linkid=236955)

  - [응용 프로그램 요청 라우팅 도움말](https://go.microsoft.com/fwlink/?linkid=236956)

다음 기능을 지원하는 부하 분산 솔루션을 확인해 보는 것이 좋습니다.

  - 계층 7 라우팅

  - 클라이언트 선호도 또는 프런트 엔드 선호도 사용

  - SSL 오프로드 사용

부하 분산 장치를 사용하는 경우 HTTPS를 사용하여 Office Web Apps 서버 통신 보안 유지 섹션에 설명된 대로 부하 분산 장치에 인증서를 설치해야 합니다.

## Office Web Apps 서버의 DNS 요구 사항

HTTPS 및 부하 분산을 사용하는 환경에서는 인증서의 FQDN(정규화된 도메인 이름)이 Office Web Apps 서버를 실행하는 서버의 IP 주소 또는 Office Web Apps 서버 팜용 부하 분산 장치에 할당된 IP 주소로 확인되도록 DNS를 업데이트해야 합니다.

## Office Web Apps 서버용 언어 팩 계획

Office Web Apps 서버 2013 언어 팩을 사용하면 SharePoint 2013 문서 라이브러리, Outlook Web App(첨부 파일 미리 보기로) 및 Lync 2013(PowerPoint 브로드캐스트로)에서 웹 기반 Office 파일을 다국어로 볼 수 있습니다. 그러나 이 기능은 호스트에 구성된 언어에 따라 달라집니다. 호스트에서 웹 기반 Office 파일을 다국어로 보려면 다음 사항을 충족해야 합니다.

  - 추가 언어에서 응용 프로그램을 실행 하려면 (예: SharePoint Server 2013 또는 Lync Server 2013 ) 호스트 구성 됩니다. 설치 하 고 호스트에서 언어팩을 구성 하는 프로세스는 독립적 Office Web Apps 서버 팜에 언어팩 설치입니다.

  - 언어는 Office Web Apps 서버 팜의 모든 서버에서 설치되며 사용 가능합니다.

[Office Web Apps 서버용 언어팩을 다운로드](https://go.microsoft.com/fwlink/p/?linkid=263945)수 있는 위치 다음과 같습니다.

## Office Web Apps 서버 토폴로지 계획

여기에 최소한 하나의 실제 컴퓨터 또는 가상 컴퓨터 Office Web Apps 서버 및 하나 이상의 호스트 (예: Lync Server 2013 또는 SharePoint 2013 실행 서버)를 실행 하는 Office Web Apps 서버 토폴로지에 포함 됩니다. 및 물론 호스트 중 하나에 연결 하 고 Office Web Apps 기능을 사용 하는 클라이언트 PC 또는 장치 필요 합니다. 해당 최소한의 토폴로지에서 더 많은 호스트가 및 조직의 요구에 맞게 필요에 따라 더 많은 Office Web Apps 서버 팜에 서버를 추가할 수 있습니다.

다음은 Office Web Apps 서버 토폴로지가 복잡해짐에 따라 유의해야 할 권장 사항의 목록입니다.

  - **중복성 계획.** 가상 컴퓨터 인스턴스를 사용하는 경우 중복에 대비하여 해당 인스턴스를 별도의 가상 컴퓨터 호스트에 배치해야 합니다. 호스트의 다른 인스턴스에서는 다른 서버 응용 프로그램을 Office Web Apps 서버와 동일한 인스턴스에서 실행하지만 않으면 서버 응용 프로그램을 실행할 수 있습니다.

  - **한 데이터 센터 유지.** Office Web Apps 서버 팜의 서버는 같은 데이터 센터에 있어야 합니다. 팜의 서버를 여러 지리적 위치에 분산시키지 마세요. 자체 Office Web Apps 서버 팜이 포함된 격리된 네트워크가 필요한 보안 요구 사항이 있는 경우를 제외하고는 팜은 일반적으로 하나만 있으면 됩니다.

  - **가급적 호스트 근처에 배치.** Office Web Apps 서버 팜은 해당 팜에서 지원하는 호스트와 같은 데이터 센터에 있지 않아도 됩니다. 그러나 편집 작업이 많은 경우 가급적 Office Web Apps 서버 팜을 호스트에 가까이 두는 것이 좋습니다. 이 사항은 Office Web Apps를 주로 Office 파일을 보는 데 사용하는 조직에는 중요하지 않습니다.

  - **연결 계획.** Office Web Apps 서버 팜의 모든 서버를 서로 간에만 연결하고, 더 넓은 네트워크에 연결하려면 역방향 프록시 부하 분산 장치 방화벽을 사용합니다.

  - **HTTP 또는 HTTPS 요청을 허용하도록 방화벽 구성.** Office Web Apps 서버를 실행하는 서버가 호스트에 대한 HTTP 또는 HTTPS 요청을 시작할 수 있도록 방화벽을 구성해야 합니다.

  - **들어오고 나가는 통신 계획.** 인터넷 연결 배포에서 나가는 모든 통신을 NAT 장치를 통해 라우팅합니다. 다중 서버 팜에서 들어오는 모든 통신을 부하 분산 장치를 통해 처리합니다.

  - **Office Web Apps 서버 팜의 모든 서버가 도메인에 가입되어 있고 같은 OU(조직 구성 단위)에 속함.** [New-OfficeWebAppsFarm](new-officewebappsfarm.md) cmdlet에서 **FarmOU** 매개 변수를 사용하여 이 OU에 속하지 않은 다른 서버가 팜에 가입하지 않도록 합니다.

  - **들어오는 모든 요청에 HTTPS(Hypertext Transfer Protocol Secure) 사용**

  - **IPsec이 네트워크에 배포되어 있으면 이를 사용하여 서버 간의 트래픽 암호화**

  - **인터넷을 사용하는 Office 기능 계획.** 클립아트 및 번역 서비스와 같은 기능이 필요한 경우에 팜 서버에서 인터넷 관련 요청을 시작할 수 없으면 Office Web Apps 서버 팜에 대한 프록시 서버를 구성해야 합니다. 그러면 외부 사이트 관련 HTTP 요청이 허용됩니다.

## Office Web Apps 서버 보안 계획

다음은 Office Web Apps 서버의 보안 지침에 대한 정보입니다.

## HTTPS를 사용하여 Office Web Apps 서버 통신 보안 유지

Office Web Apps 서버 는 HTTPS 프로토콜을 사용 하 여 SharePoint 2013 및 Lync Server 2013 와 통신할 수 있습니다. 프로덕션 환경에서 HTTPS를 사용 하는 것이 좋습니다. 할당 될 수 있는 (단일 서버를 사용 하는) 하는 경우 Office Web Apps 서버 를 실행 하는 서버 또는 부하 분산 장치 ( Office Web Apps 서버 를 실행 하는 여러 서버를 사용 하는) 하는 경우 인터넷 서버 인증서를 설치 해야 합니다.

없음 사용자 데이터를 포함 하는 테스트 환경에서는 SharePoint 2013 에 대 한 HTTP를 사용 하 고 인증서 요구 사항 건너뛸 수 있습니다. Lync Server 2013 만 HTTPS를 지원합니다.

Office Web Apps 서버에서 사용하는 인증서는 다음 요구 사항을 충족해야 합니다.

  - 인증서는 신뢰할 수 있는 인증 기관에서 발급된 것이어야 하며 SAN(주체 대체 이름) 필드에 Office Web Apps 서버 팜의 FQDN(정규화된 도메인 이름)이 포함되어 있어야 합니다. FQDN이 SAN에 없으면 인증서를 사용하려고 할 때 브라우저에 보안 경고가 표시되거나 응답이 처리되지 않습니다.

  - 인증서에는 내보낼 수 있는 개인 키가 있어야 합니다. 이 옵션은 단일 서버 팜에서 IIS(인터넷 정보 서비스) 관리자 스냅인을 사용하여 인증서를 가져올 때 기본적으로 선택됩니다.

  - 이름 필드는 신뢰할 수 있는 루트 인증 기관 저장소 내에서 고유해야 합니다. 이름 필드를 공유하는 인증서가 여러 개 있으면 New-OfficeWebAppsFarm cmdlet에서 어떤 인증서를 사용해야 하는지 알 수 없기 때문에 팜을 만들지 못합니다.

  - Office Web Apps 서버에는 특정 인증서 속성과 확장이 필요하지 않습니다. 예를 들면 클라이언트 EKU(확장된 키 사용) 확장이나 서버 EKU 확장이 필요하지 않습니다.

  - Windows Server 2012 또는 Windows Server 2012 R2에서는 "HTTP 활성화 허용" WCF(Windows Communication Foundation) 기능을 설치해야 합니다.

인증서는 다음과 같이 가져와야 합니다.

  - **단일 서버 팜의 경우** Office Web Apps 서버를 실행하는 서버에서 인증서를 직접 가져와야 합니다. 인증서를 수동으로 바인딩하지 마세요. 나중에 실행하는 New-OfficeWebAppsFarm cmdlet이 해당 작업을 수행합니다. 인증서를 수동으로 바인딩하면 서버가 다시 시작될 때마다 인증서가 삭제됩니다.

  - **부하 분산된 팜의 경우** SSL을 오프로드할 때에는 하드웨어 부하 분산 장치에서 인증서를 가져와야 하고, SSL을 오프로드하지 않을 때에는 Office Web Apps 서버 팜의 각 서버에 인증서를 설치해야 합니다.


> [!NOTE]
> 중요하지 않은 테스트 환경을 제외하고는 자체 서명된 인증서를 사용하지 마십시오.



인증서에 대 한 자세한 내용은 [SSL 인증서를 가져오는 방법](https://go.microsoft.com/fwlink/p/?linkid=269700)을 참조 하십시오.

## 하드웨어 부하 분산 장치에 SSL 오프로드 사용

새 Office Web Apps 서버 팜을 설치한 경우 SSL 오프로드는 기본적으로 Off로 설정됩니다. 그러나 팜의 각 Office Web Apps 서버에서 HTTP를 사용하여 부하 분산 장치와 통신할 수 있도록 SSL 오프로드를 On으로 설정하는 것이 좋습니다. SSL 오프로드를 On으로 설정하면 다음과 같은 이점도 얻을 수 있습니다.

  - 인증서 관리 간소화

  - 소프트 선호도 향상

  - 성능 향상

HTTP를 사용할 경우 부하 분산 장치와 Office Web Apps 서버를 실행하는 서버 간의 트래픽이 암호화되지 않으므로 네트워크 자체가 안전한지 확인해야 합니다. 전용 서브넷을 사용하면 트래픽을 보호하는 데 도움이 될 수 있습니다.

## OU 구성원 자격을 기준으로 Office Web Apps 서버 팜에 참가할 수 있는 서버 제한

권한이 없는 서버용으로 조직 구성 단위를 만들고 나서 팜을 만들 때 FarmOU 매개 변수를 지정하면 권한 없는 서버가 Office Web Apps 서버 팜에 가입하지 못하도록 할 수 있습니다. FarmOU 매개 변수에 대한 자세한 내용은 [New-OfficeWebAppsFarm](new-officewebappsfarm.md)을 참조하세요.

## 허용 목록을 사용하여 Office Web Apps 서버에 대한 호스트 액세스 제한

허용 목록은 원치 않는 호스트가 Office Web Apps 서버 팜에 연결하여 관리자 동의 없이 팜을 파일 작업에 사용하지 못하도록 하는 보안 기능입니다. 승인된 호스트를 포함하는 도메인을 허용 목록에 추가하면 Office Web Apps 서버에서 파일 검색, 메타데이터 검색, 파일 변경 등의 파일 작업 요청을 허용하는 호스트를 제한할 수 있습니다.

Office Web Apps 서버 팜을 만든 다음 허용 목록에 도메인을 추가할 수 있습니다. 허용 목록에 도메인을 추가하는 방법은 [New-OfficeWebAppsHost](new-officewebappshost.md)를 참조하세요.


> [!IMPORTANT]
> 허용 목록에 도메인을 추가하지 않으면 Office Web Apps 서버에서 모든 도메인 호스트에 대한 파일 요청을 허용합니다. 인터넷에서 Office Web Apps 서버 팜에 액세스할 수 있는 경우에는 이 목록을 비워 두지 마세요. 목록을 비워 두면 누구나 Office Web Apps 서버 팜을 사용하여 콘텐츠를 보고 편집할 수 있습니다.



## Office Web Apps 서버에서 온라인 뷰어 계획

기본적으로 온라인 뷰어 기능은 Office Web Apps 서버를 설치하고 면 사용하도록 설정됩니다. 조직에서 온라인 뷰어를 사용하려는 경우 다음 지침을 검토하세요. 온라인 뷰어 내에서 일부 기능을 사용하지 않도록 설정해야 하는 경우도 있습니다. 이 지침에서는 Windows PowerShell cmdlet [New-OfficeWebAppsFarm](new-officewebappsfarm.md) 및 [Set-OfficeWebAppsFarm](set-officewebappsfarm.md)을 사용하여 설정되는 매개 변수를 참조합니다.

## 온라인 뷰어에 대한 보안 고려 사항

온라인 뷰어를 사용하여 웹 브라우저에서 볼 수 있는 파일에는 인증이 필요하지 않아야 합니다. 즉 온라인 뷰어는 파일을 검색할 때 인증을 수행할 수 없기 때문에 이러한 파일은 공개적으로 사용할 수 있어야 합니다. 온라인 뷰어에서 사용하는 Office Web Apps 서버 팜은 인트라넷과 인터넷 모두가 아닌 둘 중 하나에만 액세스할 수 있도록 하는 것이 좋습니다. Office Web Apps 서버는 인트라넷 URL과 인터넷 URL 요청을 구분하지 않기 때문입니다. 예를 들면 인터넷 사용자가 인트라넷 URL을 요청할 수 있게 되므로, 내부 문서가 인터넷 사용자에게 제공되면 보안상 위험해질 수 있습니다.

같은 이유로 Office Web Apps 서버가 인터넷에만 연결하도록 설정하는 경우에는 온라인 뷰어에서 UNC 지원을 해제하는 것이 좋습니다. UNC 지원을 해제하려면 Windows PowerShell cmdlet [New-OfficeWebAppsFarm](new-officewebappsfarm.md)(새 팜) 또는 [Set-OfficeWebAppsFarm](set-officewebappsfarm.md)(기존 팜)을 사용하여 OpenFromUncEnabled 매개 변수를 False로 설정합니다.

추가적인 보안 예방 조치로, 온라인 뷰어는 10MB 이하의 Office 파일만 볼 수 있도록 제한됩니다.

## 온라인 뷰어의 구성 옵션

[New-OfficeWebAppsFarm](new-officewebappsfarm.md)(새 팜) 또는 [Set-OfficeWebAppsFarm](set-officewebappsfarm.md)(기존 팜)에서 다음 Windows PowerShell 매개 변수를 사용하여 온라인 뷰어를 구성할 수 있습니다.

  - **OpenFromUrlEnabled** 온라인 뷰어를 설정하거나 해제합니다. 이 매개 변수는 URL 및 UNC 경로가 포함된 파일에 대한 온라인 뷰어 기능을 제어합니다. 기본적으로 새 Office Web Apps 서버 팜을 만들 때 이 매개 변수는 False(사용 안 함)로 설정됩니다.

  - **OpenFromUncEnabled** 온라인 뷰어가 설정되어 있을 때(OpenFromUrlEnabled를 사용하여 True로 설정) 이 매개 변수는 온라인 뷰어가 UNC 경로의 파일을 표시하는 기능을 설정하거나 해제합니다. 기본적으로 이 매개 변수는 True로 설정되지만, UNC 경로에서 파일을 열 수 있도록 설정하기 전에 OpenFromUrlEnabled도 True로 설정되어 있는지 확인해야 합니다. 위에서 설명한 바와 같이 인터넷에 연결하도록 Office Web Apps 서버를 설정한 경우 이 매개 변수를 False로 설정하는 것이 좋습니다.

  - **OpenFromUrlThrottlingEnabled** 일정 기간에 지정된 서버에서 보내는 URL 요청의 열기 횟수를 제한합니다. 기본 제한 값(구성 불가)을 사용하면 Office Web Apps 서버 팜이 온라인 뷰어에서 보려는 콘텐츠에 대한 요청을 보내 단일 서버가 과도하게 소모되지 않도록 합니다.

## Office Web Apps 서버 업데이트 계획

Office Web Apps 서버를 배포하기 전에 조직에서 Office Web Apps 서버 팜의 소프트웨어 업데이트를 관리할 방법을 결정해야 합니다. 소프트웨어 업데이트는 서버 보안, 성능 및 안정성을 향상시키는 데 도움이 되지만 업데이트를 잘못 설치하면 Office Web Apps 서버에서 문제가 발생할 수 있습니다.

Microsoft 자동 업데이트 프로세스를 사용하여 Office Web Apps 서버를 업데이트하는 기능은 Office Web Apps 서버에서 지원되지 않습니다. Office Web Apps 서버는 [Office Web Apps 서버에 소프트웨어 업데이트 적용](apply-software-updates-to-office-web-apps-server.md)에 설명된 바와 같이 특정한 방식으로 업데이트해야 하기 때문입니다. Office Web Apps 서버를 자동으로 업데이트하면 사용자가 Office Web Apps에서 문서를 보거나 편집하지 못할 수 있습니다. 이 경우 Office Web Apps 서버 팜을 다시 빌드해야 합니다.

WSUS(Windows Server Update Services) 또는 WSUS를 사용하는 System Center 구성 관리자를 사용하여 업데이트를 관리하는 것이 좋습니다. WSUS를 사용하면 Office Web Apps 서버 팜의 각 서버에서 Microsoft 업데이트를 통해 출시되는 업데이트 배포를 완벽하게 관리할 수 있습니다. 예를 들어 WSUS를 사용하면 서버 팜에 자동으로 적용할 수 있는 업데이트와 수동으로 적용해야 하는 업데이트(예: Office Web Apps 서버 업데이트)를 결정할 수 있습니다. WSUS에 대한 자세한 내용은 [Windows Server Update Services](https://go.microsoft.com/fwlink/p/?linkid=294822)를 참조하세요.

WSUS 또는 System Center 구성 관리자를 사용하지 않으려면 Office Web Apps 서버 팜의 각 서버에서 Microsoft 자동 업데이트를 **자동으로 다운로드하고 설치할 때 알림**으로 설정합니다. Office Web Apps 서버 업데이트 관련 알림을 받으면 [Office Web Apps 서버에 소프트웨어 업데이트 적용](apply-software-updates-to-office-web-apps-server.md)의 단계를 따릅니다. Windows 업데이트를 적용하고 서버의 보안을 유지하려면 업데이트를 사용할 수 있다는 알림을 받았을 때 Windows 업데이트를 수락하세요.

## 참고 항목


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[Office Web Apps 서버 개요](office-web-apps-server-overview.md)  
[Office Web Apps 서버 배포](deploy-office-web-apps-server.md)  
[Office Web Apps 서버에 소프트웨어 업데이트 적용](apply-software-updates-to-office-web-apps-server.md)  


[(데스크톱 또는 모바일 장치에서 Office Web Apps에 대 한 지원)에 대 한 Office.com](https://go.microsoft.com/fwlink/p/?linkid=266657)  
  

[apply-software-updates-to-office-web-apps-server.md](apply-software-updates-to-office-web-apps-server.md)

