---
title: Set-OfficeWebAppsFarm
TOCTitle: Set-OfficeWebAppsFarm
ms:assetid: 6b0b434f-5d19-4e63-9296-cf104b2f3da8
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ219442(v=office.15)
ms:contentKeyID: 49643379
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsFarm

 

_**적용 대상:**Office Web Apps Server_

_**마지막으로 수정된 항목:**2015-03-09_

기존 Office Web Apps 서버 팜의 설정을 구성합니다.

## 구문

    Set-OfficeWebAppsFarm [-AllowCEIP <SwitchParameter>] [-AllowHttp <SwitchParameter>] [-AllowHttpSecureStoreConnections <SwitchParameter>] [-CacheLocation <String>] [-CacheSizeInGB <Nullable>] [-CertificateName <String>] [-ClipartEnabled <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DocumentInfoCacheSize <Nullable>] [-EditingEnabled <SwitchParameter>] [-ExcelAllowExternalData <SwitchParameter>] [-ExcelConnectionLifetime <Nullable>] [-ExcelExternalDataCacheLifetime <Nullable>] [-ExcelPrivateBytesMax <Nullable>] [-ExcelRequestDurationMax <Nullable>] [-ExcelSessionTimeout <Nullable>] [-ExcelWarnOnDataRefresh <SwitchParameter>] [-ExcelWorkbookSizeMax <Nullable>] [-ExternalURL <String>] [-FarmOU <String>] [-Force <SwitchParameter>] [-InternalURL <String>] [-LogLocation <String>] [-LogRetentionInDays <Nullable>] [-LogVerbosity <String>] [-MaxMemoryCacheSizeInMB <Nullable>] [-MaxTranslationCharacterCount <Nullable>] [-OpenFromUncEnabled <SwitchParameter>] [-OpenFromUrlEnabled <SwitchParameter>] [-OpenFromUrlThrottlingEnabled <SwitchParameter>] [-PicturePasteDisabled <SwitchParameter>] [-Proxy <String>] [-RecycleActiveProcessCount <Nullable>] [-RemovePersonalInformationFromLogs <SwitchParameter>] [-RenderingLocalCacheLocation <String>] [-SSLOffloaded <SwitchParameter>] [-TranslationEnabled <SwitchParameter>] [-TranslationServiceAddress <String>] [-TranslationServiceAppId <String>] [-WhatIf [<SwitchParameter>]]

## 자세한 정보

**Set-OfficeWebAppsFarm** cmdlet은 기존 Office Web Apps 서버 팜의 설정을 구성합니다.

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
<td><p><strong>AllowCEIP</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Office Web Apps 서버 팜의 모든 서버에서 CEIP(사용자 환경 개선 프로그램) 보고를 사용하도록 설정합니다.</p>
<div class="alert">

> [!IMPORTANT]
> 이 변경 내용을 적용하려면 Office Web Apps 서버 팜의 모든 서버를 다시 시작해야 합니다.


</div></td>
</tr>
<tr class="even">
<td><p><strong>AllowHttp</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>HTTP 액세스를 위해 IIS 사이트를 포트 80에서 프로비전해야 함을 나타냅니다. 모든 컴퓨터에 IPSEC(전체 암호화)가 필요한 환경 또는 중요한 파일이 포함되어 있지 않은 테스트 환경에서만 <strong>AllowHTTP</strong>를 사용합니다.</p>
<p><strong>SSLOffloaded</strong>를 사용하도록 설정하면 자동으로 사용하도록 설정됩니다.</p>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHttpSecureStoreConnections</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>HTTP 등의 비 SSL 연결을 사용하여 보안 저장소에 연결할 수 있음을 나타냅니다. 기본값은 <strong>False</strong>입니다.</p>
<p>모든 컴퓨터에 IPSEC(전체 암호화)이 필요한 환경이나 중요한 파일을 포함하지 않는 테스트 환경에서만 <strong>AllowHTTPSecureStoreConnections</strong>를 사용하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheLocation</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>렌더링된 이미지 파일을 저장하는 데 사용되는 전역 디스크 캐시의 위치를 지정합니다. 기본 위치는 <strong>%programdata%\Microsoft\OfficeWebApps\Working\d\</strong>입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheSizeInGB</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>전역 디스크 캐시의 최대 크기를 GB 단위로 지정합니다.</p>
<p>형식은 <strong>0</strong>에서 모든 양의 정수 범위의 정수 값이어야 합니다. 기본 크기는 <strong>15</strong>GB입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CertificateName</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>Office Web Apps 서버에서 HTTPS 바인딩을 만드는 데 사용하는 인증서의 이름을 지정합니다.</p>
<p>지정한 인증서가 없거나 만료된 경우 또는 지정한 값이 둘 이상의 인증서와 연결되어 있는 경우에는 오류가 기록되고 팜이 만들어지지 않습니다.</p>
<div class="alert">

> [!IMPORTANT]
> 이 값은 Office Web Apps 서버 팜에 가입하는 모든 서버에서 사용되므로 팜의 모든 서버에는 이 이름이 지정된 인증서가 있어야 합니다.


</div>
<p><strong>AllowHttp</strong> 또는 <strong>SSLOffloaded</strong> 매개 변수를 사용하는 경우에는 <strong>CertificateName</strong> 매개 변수를 지정하지 않아도 됩니다.</p>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>ClipartEnabled</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Office.com에서 Office 문서로 클립 아트를 삽입할 수 있도록 지원합니다. 이 기능을 사용하려면 서버에서 웹으로의 통신이 필요하며, 이 통신은 직접 구성하거나 <strong>Proxy</strong> 매개 변수를 통해 지정하는 프록시를 사용하여 구성합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>명령을 실행하기 전에 사용자에게 확인 메시지를 표시합니다. 자세한 내용을 확인하려면 다음 명령을 입력하세요. <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DocumentInfoCacheSize</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>메모리 캐시에 저장되는 문서 변환 레코드의 최대 수를 지정합니다.</p>
<p>기본값은 <strong>5000</strong>개 레코드입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EditingEnabled</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>브라우저에서 편집하기 위한 지원을 사용하도록 설정합니다. 기본값은 <strong>False</strong>입니다. 편집 기능을 사용하는 데 적합한 라이선스가 있는 경우에만 <strong>True</strong>로 설정합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelAllowExternalData</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Excel Web App 통합 문서(외부 데이터에 대한 연결이 포함됨)에서 지원되는 외부 데이터 새로 고침을 사용하도록 설정합니다. 기본값은 <strong>True</strong>입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelConnectionLifetime</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>Excel Web App에 대한 외부 데이터 연결 기간을 초 단위로 지정합니다. 기본값은 <strong>1800</strong>초입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelExternalDataCacheLifetime</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>Excel Web App의 외부 데이터 캐시 수명 기간을 초 단위로 지정합니다. 기본값은 <strong>300</strong>초입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelPrivateBytesMax</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>Excel Web App에서 사용하는 최대 전용 바이트를 MB 단위로 지정합니다. <strong>-1</strong>로 설정하면 최대 전용 바이트가 컴퓨터 실제 메모리의 50%를 사용합니다.</p>
<p>형식은 <strong>-1</strong> 또는 양의 정수여야 합니다. 기본값은 <strong>-1</strong>입니다.</p>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelRequestDurationMax</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>세션의 단일 요청에 허용되는 최대 기간을 초 단위로 지정합니다. 이 시간이 경과하면 요청 시간이 초과됩니다.</p>
<p>형식은 <strong>-1</strong>(제한 없음) 또는 <strong>1</strong>에서 <strong>2073600</strong> 범위의 정수여야 합니다. 기본값은 <strong>300</strong>입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelSessionTimeout</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>사용자 작업이 없는 상태에서 세션이 Excel Web App에서 활성 상태로 유지되는 시간을 초 단위로 지정합니다. 유효한 값은 다음과 같습니다.</p>
<p><strong>-1</strong> Session never expires.</p>
<p><strong>0</strong>: 단일 요청이 끝나면 세션이 만료됩니다.</p>
<p><strong>1</strong> ~ <strong>2073600</strong>: 세션이 1초에서 24일까지 활성 상태로 유지됩니다. 기본값은 <strong>450</strong>입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelWarnOnDataRefresh</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Excel Web App에서 데이터를 새로 고칠 때 표시되는 경고 대화 상자를 설정하거나 해제합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelWorkbookSizeMax</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>로드할 수 있는 통합 문서의 최대 크기를 메가바이트(MB) 단위로 지정합니다.</p>
<p>형식은 <strong>1</strong>에서 <strong>2000</strong> 범위의 정수 값이어야 합니다. 기본값은 <strong>10</strong>입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalURL</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>클라이언트가 인터넷에서 Office Web Apps 서버 팜에 액세스하는 데 사용하는 URL 루트를 지정합니다. 부하 분산된 다중 서버 Office Web Apps 서버 팜의 경우 외부 URL은 외부 연결 부하 분산 장치의 IP 주소에 바인딩됩니다.</p>
<p>Office Web Apps 서버 팜에는 URL이 하나 이상 필요하며, URL은 <strong>ExternalURL</strong> 또는 <strong>InternalURL</strong>을 사용하여 설정됩니다. 내부 URL과 외부 URL을 둘 다 설정할 수도 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FarmOU</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>서버가 Office Web Apps 서버 팜에 가입하기 위해 구성원으로 속해 있어야 하는 Active Directory OU(조직 구성 단위)의 이름을 지정합니다. 권한이 없는 서버(OU에 없는 서버)가 Office Web Apps 서버 팜에 가입하지 못하도록 하려면 이 매개 변수를 사용합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>&quot;예&quot;로 대답하여 모든 사용자 프롬프트를 표시하지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>InternalURL</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>클라이언트가 인트라넷에서 Office Web Apps 서버 팜에 액세스하는 데 사용해야 하는 URL 루트를 지정합니다.</p>
<p>Office Web Apps 서버 팜에는 URL이 하나 이상 필요하며, URL은 <strong>ExternalURL</strong> 또는 <strong>InternalURL</strong>을 사용하여 설정됩니다. 내부 URL과 외부 URL을 둘 다 설정할 수도 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LogLocation</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>작업 로그가 저장되는 로컬 컴퓨터의 위치를 지정합니다.</p>
<p>이 위치는 팜의 모든 서버에 적용되며 서버별로 사용자 지정할 수 없습니다. 기본 위치는 <strong>%programdata%\Microsoft\OfficeWebApps\Data\Logs\ULS\</strong>입니다.</p>
<p>로그가 저장되는 드라이브에 디스크 공간이 충분한지 확인해야 합니다.</p>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="even">
<td><p><strong>LogRetentionInDays</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>로그 항목이 저장되는 기간(일)을 지정합니다. 구성된 날짜보다 오래된 로그 항목은 잘립니다.</p>
<p>형식은 <strong>0</strong>에서 <strong>365</strong> 범위의 정수 값이어야 합니다. 기본값은 <strong>7</strong>일입니다.</p>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>LogVerbosity</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>추적 로그 파일에 저장되는 정보의 양을 지정합니다. 값은 다음과 같습니다.</p>
<p><strong>VerboseEX</strong>: 추적 로그 파일에 낮은 수준의 세부 정보를 씁니다. 분량이 많은 추적의 경우에 유용합니다.</p>
<p><strong>Verbose</strong>: 추적 로그 파일에 낮은 수준의 세부 정보를 씁니다.</p>
<p><strong>Medium</strong>: 추적 로그 파일에 중간 수준의 세부 정보를 씁니다.</p>
<p><strong>High</strong>: 추적 로그 파일에 높은 수준의 세부 정보를 씁니다.</p>
<p><strong>Monitorable</strong>: 모니터링해야 하는 비정상 코드 경로 및 작업을 나타내는 추적을 씁니다.</p>
<p><strong>Unexpected</strong>: 모니터링해야 하는 예기치 않은 코드 경로 및 작업을 나타내는 추적을 씁니다.</p>
<p><strong>None</strong>: 추적 로그 파일에 추적 정보를 쓰지 않습니다.</p>
<div class="alert">

> [!IMPORTANT]
> <STRONG>LogVerbosity</STRONG>를 오랫동안 낮은 수준으로 유지하면 성능이 저하됩니다.


</div>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="even">
<td><p><strong>MaxMemoryCacheSizeInMB</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>렌더링 캐시에서 사용할 수 있는 최대 메모리 양을 MB 단위로 지정합니다.</p>
<p>형식은 <strong>0</strong>에서 모든 양의 정수 범위의 정수 값이어야 합니다. 기본 크기는 <strong>1024</strong>MB입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxTranslationCharacterCount</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>번역하려는 문서에 포함할 수 있는 최대 문자 수를 지정합니다.</p>
<p>형식은 정수 값이어야 합니다. 값은 0(제한 없음)으로 설정하거나 <strong>2000</strong>에서 <strong>2,000,000</strong> 사이의 값으로 설정할 수 있습니다. 기본값은 <strong>125,000</strong>입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUncEnabled</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>온라인 뷰어를 사용하여 UNC 경로에서 Office 파일을 볼 수 있는 기능을 설정하거나 해제합니다.</p>
<p>온라인 뷰어에서 UNC 경로의 파일을 표시할 수 있도록 하려면 먼저 OpenFromUrlEnabled를 True로 설정해야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OpenFromUrlEnabled</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>온라인 뷰어를 사용하여 URL 또는 UNC 경로의 Office 파일을 볼 수 있는 기능을 설정하거나 해제합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUrlThrottlingEnabled</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>일정 기간 동안 지정된 서버로부터의 URL에서 열기 요청 수를 제한합니다. 기본 제한 값(구성할 수 없음)을 사용하는 경우 Office Web Apps 서버 팜이 온라인 뷰어에서 보려는 콘텐츠에 대한 요청을 단일 서버에 너무 많이 보내지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PicturePasteDisabled</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>사용자가 웹 페이지의 이미지를 Office Web Apps에 붙여 넣을 수 있는 기능을 해제합니다. 기본값은 <strong>False</strong>입니다. <strong>OpenFromURLEnabled</strong>를 <strong>True</strong>로 설정한 경우 <strong>PicturePasteDisabled</strong>를 설정하지 않거나 <strong>False</strong>로 설정하면 사용자가 Office Web Apps에 이미지를 붙여 넣을 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Proxy</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>외부 사이트에 대한 HTTP 요청을 허용하도록 구성된 프록시 서버의 URL을 지정합니다. 보통 <strong>ClipartEnabled</strong> 및 <strong>TranslationEnabled</strong> 매개 변수와 함께 구성됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecycleActiveProcessCount</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Nullable</p></td>
<td><p>단일 Word 또는 PowerPoint 프로세스를 재활용할 때까지 프로세스에서 렌더링할 수 있는 파일 수를 지정합니다.</p>
<p>형식은 <strong>1</strong>에서 <strong>1000</strong> 범위의 정수 값이어야 합니다. 기본값은 <strong>5</strong>입니다.</p>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="even">
<td><p><strong>RemovePersonalInformationFromLogs</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Office Web Apps 서버 로그에서 개인 정보를 최대한 삭제하고 값을 SHA256 해시로 바꿉니다. 잠재적으로 다음과 같은 정보가 삭제될 수 있습니다.</p>
<ul>
<li><p>문서 이름 및 URL</p></li>
<li><p>IP 주소</p></li>
<li><p>전자 메일 주소</p></li>
<li><p>사용자 이름</p></li>
</ul>
<p>기본값은 <strong>False</strong>입니다. 이 매개 변수를 사용해도 개인 정보가 Office Web Apps 서버 로그에 기록될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RenderingLocalCacheLocation</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>Word 및 PowerPoint Viewing Services에서 사용할 임시 캐시 위치를 지정합니다.</p>
<p>기본 위치는 <strong>%programdata%\Microsoft\OfficeWebApps\Working\waccache\</strong>입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SSLOffloaded</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>SSL이 부하 분산 장치로 오프로드되었음을 Office Web Apps 서버 팜의 서버에 알립니다. <strong>SSLOffloaded</strong>를 사용하도록 설정하면 웹 응용 프로그램이 로컬 서버의 포트 80(HTTP)에 바인딩됩니다. 그러나 CSS, 이미지 등의 다른 리소스를 참조하는 HTML은 해당 참조에 대해 HTTPS URL을 사용합니다.</p>
<div class="alert">

> [!IMPORTANT]
> 팜의 모든 서버를 다시 시작해야 이 변경 내용이 적용됩니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationEnabled</strong></p></td>
<td><p>선택</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><div class="alert">

> [!IMPORTANT]
> 언어 간에 텍스트를 번역하는 온라인 서비스인 Microsoft Translator를 사용하여 문서를 자동으로 번역할 수 있도록 지원합니다. 번역된 파일은 Word Web App에 표시됩니다. Microsoft Translator는 온라인 서비스이므로 서버에서 웹으로의 통신을 사용하도록 설정해야 합니다. 이 통신은 직접 구성하거나 <STRONG>Proxy</STRONG> 매개 변수를 통해 지정하는 프록시를 사용하여 구성합니다.<BR>Microsoft Translator에서는 번역 품질 개선을 위해 데이터를 수집할 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p><strong>TranslationServiceAddress</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>번역 요청을 보낼 번역 서버의 URL을 지정합니다. 기본값은 Microsoft Translator 온라인 서비스입니다. 일반적으로는 번역 서비스를 변경해야 하는 경우가 아니면 이 매개 변수를 사용하지 않습니다.</p>
<div class="alert">

> [!IMPORTANT]
> 이 변경 내용을 적용하려면 Office Web Apps 서버 팜의 모든 서버를 다시 시작해야 합니다.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationServiceAppId</strong></p></td>
<td><p>선택</p></td>
<td><p>System.String</p></td>
<td><p>번역 서비스의 응용 프로그램 ID를 지정합니다. 기본값은 Office Web Apps의 공용 응용 프로그램 ID입니다. 일반적으로는 추가 서비스에 대해 Microsoft Translator와 협상했으며 해당 서비스에서 개인 응용 프로그램 ID를 제공한 경우가 아니면 이 매개 변수를 사용하지 않습니다.</p></td>
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

    Set-OfficeWebAppsFarm -ClipartEnabled:$true

이 예제에서는 Office.com의 클립 아트를 삽입할 수 있도록 설정합니다.

\---------------예제 2---------------

    Set-OfficeWebAppsFarm -EditingEnabled:$true

이 예제에서는 Office Web Apps에 대해 편집 기능을 사용하도록 설정합니다.

\------------------예제 3---------------------

    Set-OfficeWebAppsFarm -OpenFromUncEnabled:$false

이 예제에서는 UNC 경로에서 Office 파일을 보는 기능을 해제합니다.

## 참고 항목


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[Office Web Apps 서버의 콘텐츠 로드맵](content-roadmap-for-office-web-apps-server.md)  
[인프라 배포: Office Web Apps 서버](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

