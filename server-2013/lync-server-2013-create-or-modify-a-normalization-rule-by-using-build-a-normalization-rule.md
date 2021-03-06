﻿---
title: 'Lync Server 2013: 正規化ルールの構築を使用した正規化ルールの作成または変更'
TOCTitle: 正規化ルールの構築を使用した正規化ルールの作成または変更
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48273906
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での正規化ルールの構築を使用した正規化ルールの作成または変更

 

_**トピックの最終更新日:** 2012-11-01_

Lync Server コントロール パネルで正規化ルールを作成または変更する場合は、次の手順を実行します。あるいは、正規化ルールを手動で作成または変更する場合は、「[Lync Server 2013 での手動による正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)」を参照してください。

## \[正規化ルールの構築\] を使用してルールを定義するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  (オプション) 「[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)」の手順 11 まで、または「[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)」の手順 10 までの手順に従います。

4.  \[**新しい正規化ルール**\] または \[**正規化ルールの編集**\] の \[**名前**\] に、正規化される番号のパターンについてわかりやすい名前 (たとえば、 **5DigitExtension** ) を入力します。

5.  (オプション) \[**説明**\] ボックスに、正規化ルールの説明を入力します (たとえば、"5 桁の内線番号を変換")。

6.  \[**正規化ルールの構築**\] で、次のフィールドに値を入力します。
    
      - **開始桁の数字**   (オプション) パターンと照合するダイヤル番号の先頭数字を指定します。たとえば、425 で始まるダイヤル番号とパターンが一致するようにする場合は、「**425** 」と入力します。
    
      - **長さ**   一致パターンの桁数を指定し、そのパターンがこの長さと完全に一致するようにするのか、少なくともこの長さのダイヤル番号と一致するようにするのか、または任意の長さのダイヤル番号と一致するようにするのかを選択します。
    
      - **削除する桁数**   (オプション) パターンと照合するダイヤル番号の先頭から削除する桁数を指定します。
    
      - **追加する数字**   (オプション) パターンと照合するダイヤル番号に追加する何桁かの数字を指定します。
    
    これらのフィールドに入力する値は、\[**一致パターン**\] および \[**変換ルール**\] に反映されます。たとえば、\[**開始桁の数字**\] を空にして \[**長さ**\] フィールドに「**7** 」と入力し、\[**完全一致**\] を選択し、\[**削除する桁数**\] で「**0** 」と指定すると、\[**一致パターン**\] に表示される正規表現は次のようになります。
    
    **^(\\d{7})$**

7.  \[**変換ルール**\] で、変換される E.164 電話番号の形式のパターンを次のように指定します。
    
      - 一致パターンで指定した桁数を表す値。たとえば、一致パターンが **^(\\d{7})$** の場合、変換ルールの **$1** は 7 桁のダイヤル番号を表します。
    
      - (オプション) \[**追加する数字**\] フィールドに値を入力して、変換された番号に付加する数字を指定します (たとえば、「**+1425** 」)。
    
    たとえば、\[**一致パターン**\] にダイヤル番号のパターンとして **^(\\d{7})$** が含まれており、\[**変換ルール**\] に E.164 電話番号のパターンとして **+1425$1** が含まれている場合、5550100 はルールによって正規化されて +14255550100 となります。

8.  (オプション) 正規化ルールによって電話番号が組織の内線番号になる場合は、\[**内線番号**\] を選択します。

9.  (オプション) 正規化ルールをテストする番号を入力し、\[**次へ**\] をクリックします。テスト結果は、\[**テストする番号の入力**\] の下に表示されます。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>テストにまだ合格していない正規化ルールは、保存しておいて後で再構成できます。詳細については、「<a href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


10. \[**OK**\] をクリックして正規化ルールを保存します。

11. \[**OK**\] をクリックしてダイヤル プランを保存します。

12. \[**ダイヤル プラン**\] ページで \[**確定**\] をクリックして、\[**すべて確定**\] をクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>正規化ルールを作成または変更するときにはいつでも、[<strong>すべて確定</strong>] コマンドを実行して構成の変更を公開する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


## 関連項目

#### タスク

[Lync Server 2013 での手動による正規化ルールの作成または変更](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Lync Server 2013 でのダイヤル プランの作成](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### その他のリソース

[Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

