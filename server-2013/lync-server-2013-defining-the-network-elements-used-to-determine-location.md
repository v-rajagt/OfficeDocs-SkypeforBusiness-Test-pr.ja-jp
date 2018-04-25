﻿---
title: 'Lync Server 2013: 場所の判断に使用するネットワーク要素の定義'
TOCTitle: 場所の判断に使用するネットワーク要素の定義
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48272536
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での場所の判断に使用するネットワーク要素の定義

 

_**トピックの最終更新日:** 2012-10-29_

クライアントの場所の自動検出をサポートするように Lync Server インフラストラクチャを設定する場合は、発信者を場所にマップするために使用するネットワーク要素を最初に決定する必要があります。Lync Server 2013 では、次のレイヤー 2 およびレイヤー 3 のネットワーク要素を場所と関連付けることができます。

  - ワイヤレス アクセス ポイント (WAP) の BSSID (Basic Service Set Identification) アドレス (レイヤー 2)

  - LLDP スイッチ ポート (レイヤー 2)

  - LLDP スイッチ シャーシ ID (レイヤー 2)

  - IP サブネット (レイヤー 3)

  - クライアント MAC アドレス (レイヤー 2)

これらのネットワーク要素は、優先順位の高い順に記されています。複数のネットワーク要素を使用してクライアントを特定できる場合、Lync Server では、この優先順位に基づいて使用するメカニズムを決定します。

以下のセクションでは、各ネットワーク要素を使用する方法の詳細を説明します。


> [!IMPORTANT]
> ネットワーク要素を使用して発信者を場所にマップするときは、場所情報サービス データベースを最新の状態に維持することが最も重要です。ネットワーク要素を追加または変更する場合は (WAP の追加など)、場所データベースの古いエントリを削除して、新しいエントリを追加する必要があります。



## ワイヤレス アクセス ポイント

クライアントがワイヤレスでネットワークに接続する場合、場所の要求では WAP の BSSID アドレスを使用してその場所を特定します。クライアントがローミングしている場合は、示される WAP が最も近いものではない可能性があり、建物の別の階の WAP が選択される可能性さえあります。場所がおおよその場所であることを示すには、場所の値の前に Near または Close to という記述子を追加します。

場所に関するこの方法では、各 WAP の BSSID が静的なものであることを前提としています。ただし、動的に割り当てられた BSSID を WAP ベンダーが使用している場合は、WAP から取得された BSSID が変化する可能性があり (こうした変化は WAP 構成の変更に引き続いて発生します)、ワイヤレス クライアントは場所の情報を受け取れない状況で放置される可能性があります。こうした事態を防ぐには、各 WAP で使用される可能性のあるすべての BSSID アドレスに対して、ERL を備えた 場所情報サービス データベースを設定する必要があります。

## LLDP ポートおよびスイッチ

LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) をサポートしている管理されたイーサネット スイッチは、自らの ID とポート情報を LLDP-MED に準拠したクライアントにアドバタイズできます。さらにこうしたクライアントは、デバイスの場所を提供するために場所データベースに対して照会できます。ERL はスイッチ シャーシ ID に対してのみ関連付けることも、ポート レベルにまで詳細に記述することもできます。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lync Server 2013 が LLDP-MED を使用した場所の特定をサポートするのは、Windows 8 で実行する Lync Phone Edition デバイスおよび Lync 2013 の場合だけです。スイッチ レベルのレイヤー 2 データを使用した他の PC ベースの有線 Lync クライアントの場所の特定が必要な場合は、クライアント MAC アドレスによる方法を使用する必要があります。</td>
</tr>
</tbody>
</table>


## サブネット

レイヤー 3 IP サブネットは、クライアントの場所の自動検出に使用できるすべての Lync Server クライアントによってサポートされるメカニズムを実現します。IP サブネットの使用は有線クライアントを構成および管理する最も簡単な場所特定の方法です。ただし、サブネットの使用を決定する前に、以下の質問を参考にして、サブネットの場所の特異性がクライアントを正確に特定するうえで十分に細かいかどうかを判断してください。

  - 1 つ以上のクライアント サブネットで複数の階をカバーしていますか。

  - 1 つ以上のサブネットで複数の建物をカバーしていますか。

  - どれほどのフロア領域が各クライアント サブネットでカバーされていますか。

サブネットでカバーする領域が広すぎる場合は、別のメカニズムを使用したクライアントの特定が必要になることがあります。ただし、たとえ実用的であったとしても、サードパーティによる SNMP ベースのソリューションの費用と複雑さを受け入れるよりは、ERL の場所の特異性に関する要件を満たすように顧客が自らの IP サブネット処理を再編成することをお勧めします。

## クライアント MAC アドレス

クライアント コンピューターの MAC アドレスを使用して発信者を特定するには、管理されたイーサネット スイッチが必要であり、これらのスイッチに接続しているか、これらのスイッチ経由で接続している Lync クライアントの MAC アドレスを検出できるサードパーティ SNMP ソリューションを展開する必要があります。こうした SNMP ソリューションは、管理されたスイッチの継続的なポーリングによって各ポートに接続されているエンドポイント MAC アドレスの現在のマッピングを取得し、対応するポート ID を取得します。場所情報サービスに対する Lync クライアントの要求時には、場所情報サービスがクライアントの MAC アドレスを使用してサードパーティ アプリケーションへの問い合わせを行い、一致するすべての IP アドレスとポート ID を返します。場所情報サービスは、この情報を使用して、公開されているレイヤー 2 ワイヤマップに対して一致するレコードを問い合わせ、その場所をクライアントに返します。このオプションを使用する場合は、SNMP アプリケーションと公開されている場所データベースのレコードの間でスイッチ ポート ID の整合が取れていることを確認してください。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>一部のサードパーティ SNMP ソリューションは、管理されていないアクセス スイッチをサポートできます。Lync クライアントにサービスを提供しているスイッチが管理されておらず、管理されているディストリビューション スイッチへのアップリンクを持つ場合、管理されているスイッチはアクセス スイッチに接続されたクライアントの MAC アドレスを SNMP ソリューションにレポートできます。この情報によって、場所情報サービスはユーザーの場所を特定できます。ただし、1 つの ERL を管理されていないスイッチ上のすべてのポートに割り当てることしかできません。そのため、場所の特異性はアクセス スイッチのポート レベルではなく、シャーシ レベルでのみ使用できます。</td>
</tr>
</tbody>
</table>
