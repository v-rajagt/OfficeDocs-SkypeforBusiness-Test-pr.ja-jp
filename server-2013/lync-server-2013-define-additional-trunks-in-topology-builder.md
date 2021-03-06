﻿---
title: 'Lync Server 2013: トポロジ ビルダーでの追加トランクの定義'
TOCTitle: トポロジ ビルダーでの追加トランクの定義
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49887188
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのトポロジ ビルダーでの追加トランクの定義

 

_**トピックの最終更新日:** 2012-10-04_

以下の手順に従って、 トポロジ ビルダーを使用して、 *ピア* と 仲介サーバーを関連付けることのできる追加トランクを定義します。ピアは、 エンタープライズ VoIP が有効になっているユーザーに公衆交換電話網 (PSTN) への接続を提供します。ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。トランクは、 仲介サーバーとピア間のこの接続を定義します。 仲介サーバーごとに複数のトランクを定義できます。 仲介サーバーを複数のピアと関連付けることができます。

トランクとは、 仲介サーバーと、タプルによって一意に識別されるゲートウェイとの間の論理接続のことです。

{ 仲介サーバー FQDN、 仲介サーバー リッスン ポート (TLS または TCP) : ゲートウェイ IP および FQDN、ゲートウェイ リッスン ポート}

<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>このトピックでは、「展開」のドキュメントの「<a href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 での、トポロジ ビルダーを使用したゲートウェイの定義</a>」で説明されているように、少なくとも 1 つの併置またはスタンドアロン 仲介サーバーまたはプールを使用して、PSTN ゲートウェイとルート トランクを設定していることを想定しています。</td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>このトピックでは、「展開」のドキュメントの「<a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync Server 2013 でフロントエンド プールまたは Standard Edition サーバーを定義および構成する</a>」および「<a href="lync-server-2013-publish-the-topology.md">Lync Server 2013 でトポロジを公開する</a>」で説明されているように、少なくとも 1 つの中央サイトで少なくとも 1 つの フロント エンド プールまたは Standard Edition サーバーを設定していることを想定しています。</td>
</tr>
</tbody>
</table>


## 仲介サーバーとゲートウェイ ピア間の追加トランクを定義するには

1.  トポロジ ビルダーを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server トポロジ ビルダー**\] の順にクリックします。

2.  Lync Server 2013、サイト名、\[**共有コンポーネント**\] の順に移動して、\[**トランク**\] ノードを右クリックし、\[**新しいトランク**\] をクリックします。
    
    ![Lync Server、トポロジ ビルダーのファイル構造画面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server、トポロジ ビルダーのファイル構造画面")

3.  \[**新しいトランクの定義**\] で、トランクを一意に識別するためのフレンドリ名を指定します。2 つのトランクに同じ名前を付けることはできません。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合、 仲介サーバーのピアの IP アドレスの代わりに、FQDN を指定する必要があります。</td>
    </tr>
    </tbody>
    </table>


4.  \[**PSTN ゲートウェイの関連付け**\] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。
    
    ![トランク用 PSTN ゲートウェイ ピアのプロパティ設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "トランク用  PSTN ゲートウェイ ピアのプロパティ設定")

5.  \[**PSTN ゲートウェイのリッスン ポート**\] で、このトランクと関連付けられる 仲介サーバーからピア (PSTN ゲートウェイ、IP-PBX、または SBC) が SIP メッセージを受け取るリッスン ポートを入力します。既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。既定の 存続可能ブランチ アプライアンス ポートは、TCP 用が 5081 で、TLS 用が 5082 です。

6.  \[**SIP トランスポート プロトコル**\] で、ピアが使用するトランスポートの種類をクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>セキュリティ上の理由により、TLS を使用可能な 仲介サーバーのピアを展開することを強くお勧めします。</td>
    </tr>
    </tbody>
    </table>


7.  \[**関連付けられた仲介サーバー**\] で、 仲介サーバープールを選択してこのピアのルート トランクと関連付けます。

8.  \[**関連付けられている仲介サーバーのポート**\] で、 仲介サーバーがピアから SIP メッセージを受け取るリッスン ポートを入力します。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Lync Server 2013 の複数トランク サポートを使用して、同じ [<strong>仲介サーバー ポートの関連付け</strong>] および [<strong>IP/PSTN ゲートウェイのリッスン ポート</strong>] で、異なるトランク名を持つ 2 つのトランクを定義できません。</td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Lync Server 2013 の複数トランク サポートを使用して、複数のピアと通信する仲介サーバーで複数の SIP 信号ポートを定義できます。トランクを定義するときは、[<strong>仲介サーバー ポートの関連付け</strong>] の数は、仲介サーバーが許可するそれぞれのプロトコルのリッスン ポートの範囲内にする必要があります。このポート範囲は、Lync Server 2013 および仲介サーバー プールで定義されます。関連する仲介サーバー プールを右クリックし、[<strong>プロパティの編集</strong>] を選択します。&quot;<strong>リッスン ポート</strong>&quot; フィールドでポート範囲を指定します。</td>
    </tr>
    </tbody>
    </table>


9.  \[**OK**\] をクリックします。

## 関連項目

#### タスク

[Lync Server 2013 でのトポロジ ビルダーによるトランクの変更](lync-server-2013-modify-a-trunk-in-topology-builder.md)

