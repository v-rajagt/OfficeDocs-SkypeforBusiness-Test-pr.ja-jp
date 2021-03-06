﻿---
title: ネットワーク サイトの作成または変更
TOCTitle: ネットワーク サイトの作成または変更
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48271726
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク サイトの作成または変更

 

_**トピックの最終更新日:** 2012-10-08_

ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。Microsoft Lync Server 2013 コントロール パネルを使用して、サイトを構成し地域に関連付けることができます。たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。Lync Server コントロール パネルで、ネットワーク サイトを作成、変更、または削除できます。ネットワーク サイトを作成または変更するには、以下の手順を使用します。既存のネットワーク サイトを削除することの詳細については、「[既存のネットワーク サイトの削除](lync-server-2013-deleting-an-existing-network-site.md)」を参照してください。

## ネットワーク サイトを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**サイト**\] をクリックします。

4.  \[**サイト**\] ページで、\[**新規**\] をクリックします。

5.  \[**新しいサイト**\] で、\[**名前**\] フィールドにサイトの名前を入力します。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>サイトの名前は、Lync Server 2013 展開内で一意である必要があります。</td>
    </tr>
    </tbody>
    </table>


6.  \[**地域**\] ドロップダウン リストで、このサイトに関連付けるネットワーク地域を選択します。

7.  (オプション) このサイトに対する音声またはビデオ通話に帯域幅制限を設定する場合は、\[**帯域幅ポリシー**\] ドロップダウン リストで該当する設定値を備える帯域幅ポリシー プロファイルを選択します。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>[<strong>ネットワーク構成</strong>] グループの [<strong>ポリシーのプロファイル</strong>] ページでは、利用可能な帯域幅ポリシー プロファイルの詳細を表示したり、新しい帯域幅ポリシー プロファイルを作成したりできます。詳細については、「<a href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">帯域幅ポリシー プロファイルの作成または変更</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


8.  (オプション) このサイトに、場所に関する設定を提供する場合は、\[**場所のポリシー**\] ドロップダウン リストで場所のポリシーを選択します。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>場所のポリシーは、特定の Enhanced 9-1-1 (E9-1-1) とクライアントの場所に関連する設定をサイトに割り当てます。 [<strong>ネットワーク構成</strong>] グループの [<strong>場所のポリシー</strong>] ページでは、利用可能な場所のポリシーの詳細を表示したり、新しい場所のポリシーを作成したりできます。詳細については、「<a href="lync-server-2013-viewing-location-policy-information.md">場所ポリシー情報の表示</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


9.  (オプション) \[**説明**\] フィールドに値を入力して、名前だけでは表現することのできないこのサイトの詳細情報を提供します。

10. \[**確定**\] をクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>新しいネットワーク サイトを作成するとき、[<strong>関連付けられたサブネット</strong>] テーブルは使用しません。 サブネットの作成または変更時に、サブネットをサイトに関連付けます。詳細については、「<a href="lync-server-2013-create-or-modify-network-subnets.md">ネットワーク サブネットの作成または変更</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


## ネットワーク サイトを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**サイト**\] をクリックします。

4.  \[**サイト**\] ページで、変更するサイトをクリックします。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

6.  \[**サイトの編集**\] ページでは、サイトに関連付けられた、説明、地域、帯域幅ポリシー プロファイル、および場所のポリシーを変更できます。詳細については、このトピックの「ネットワーク サイトを作成するには」を参照してください。

7.  \[**確定**\] をクリックします。

このページの \[**関連付けられたサブネット**\] テーブルを変更することはできません。 関連付けられたサブネットの一覧は、参照のために用意されており、サイトの設定を変えるとどのサブネットが影響を受けるかを確認できます。

## ネットワーク サイトを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**サイト**\] をクリックします。

4.  \[**サイト**\] ページで、削除するサイトをクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>1 つ以上のサイトを一度に削除できます。 これを実行するには、Ctrl キーを押しながら、複数のサイトを選択します。 また、すべてのサイトを選択するには、[<strong>編集</strong>] メニューの [<strong>すべて選択</strong>] をクリックします。</td>
    </tr>
    </tbody>
    </table>


5.  \[**編集**\] メニューの \[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。
    

    > [!WARNING]
    > ただし、ネットワーク サイトがネットワーク サブネットに関連付けられている場合は、サイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。 サイトがサブネットに関連付けられているかどうかを確認するには、そのサイトをクリックして、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。



## 関連項目

#### タスク

[既存のネットワーク サイトの削除](lync-server-2013-deleting-an-existing-network-site.md)  

#### その他のリソース

[New-CsNetworkSite](new-csnetworksite.md)  
[Set-CsNetworkSite](set-csnetworksite.md)  
[Remove-CsNetworkSite](remove-csnetworksite.md)  
[Get-CsNetworkSite](get-csnetworksite.md)

