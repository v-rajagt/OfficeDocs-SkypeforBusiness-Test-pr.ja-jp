﻿---
title: 'Lync Server 2013: ダイヤル プランの作成'
TOCTitle: ダイヤル プランの作成
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48273663
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのダイヤル プランの作成

 

_**トピックの最終更新日:** 2013-10-24_

新しいダイヤル プランを作成するには、次の手順を実行します。ダイヤル プランを編集する場合は、「[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)」を参照してください。

## ダイヤル プランを作成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声ルーティング**\] をクリックし、\[**ダイヤル プラン**\] をクリックします。

4.  \[**ダイヤル プラン**\] ページで、\[**新規**\] をクリックしてダイヤル プランのスコープを選択します。
    
      - \[**サイト ダイヤル プラン**\] は、ユーザー ダイヤル プランが割り当てられているユーザーおよびグループを除く、サイト全体に適用されます。ダイヤル プランのスコープに \[**サイト**\] を選択した場合、\[**サイトの選択**\] ダイアログ ボックスでサイトを選択する必要があります。サイトに対して既にダイヤル プランが作成されている場合、そのサイトは \[**サイトの選択**\] ダイアログ ボックスに表示されません。
    
      - \[**プール ダイヤル プラン**\] は、公衆交換電話網 (PSTN) ゲートウェイまたはレジストラーに適用できます。ダイヤル プランのスコープに \[**プール**\] を選択した場合、\[**サービスの選択**\] ダイアログ ボックスで PSTN ゲートウェイまたはレジストラーを選択します。サービス (PSTN ゲートウェイまたはレジストラー) に対して既にダイヤル プランが作成されている場合、そのサービスは一覧に表示されません。
    
      - \[**ユーザー ダイヤル プラン**\] は、特定のユーザーまたはグループに適用できます。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>ダイヤル プランのスコープを選択した後で、スコープを変更することはできません。</td>
    </tr>
    </tbody>
    </table>


5.  ユーザー ダイヤル プランを作成する場合、\[**新しいダイヤル プラン**\] ダイアログ ボックスの \[**名前**\] フィールドにわかりやすい名前を入力します。名前を保存した後で、名前を変更することはできません。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>サイト ダイヤル プランの場合、[<strong>名前</strong>] フィールドにサイト名が設定され、変更することはできません。<br />
    プール ダイヤル プランの場合、[<strong>名前</strong>] フィールドに PSTN ゲートウェイまたはレジストラーの名前が設定され、変更することはできません。</td>
    </tr>
    </tbody>
    </table>


6.  \[**簡単な名前**\] フィールドには、\[**名前**\] フィールドに表示されたのと同じ名前が設定されます。必要に応じてこのフィールドを編集し、ダイヤル プランを適用するサイト、サービス、またはユーザーを説明する、よりわかりやすい名前を指定できます。
    

    > [!IMPORTANT]
    > [<STRONG>簡単な名前</STRONG>] は、Lync Server 展開内のすべてのダイヤル プランの中で一意である必要があります。英字、数字、ハイフン (-)、ピリオド (.)、またはアンダースコア (_) の Unicode 文字を 256 文字まで使用できます。<BR><STRONG>サポートされていない</STRONG>文字には、スペースや RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt) で定義されている予約文字があります。[<STRONG>簡単な名前</STRONG>] で <STRONG>使用できない</STRONG>予約文字は次の通りです。<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","



7.  (オプション) \[**説明**\] フィールドに、追加する、ダイヤル プランに関するわかりやすい情報を入力できます。

8.  (オプション) このダイヤル プランをダイヤルイン アクセス番号の地域として使用する場合は、\[**ダイヤルイン会議の地域**\] を指定します。このダイヤル プランをダイヤルイン アクセス番号で使用しない場合は、このフィールドを空のままにします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>ダイヤルイン会議の地域は、ダイヤルイン会議アクセス番号を、1 つまたは複数のダイヤル プランに関連付けるのに必要です。</td>
    </tr>
    </tbody>
    </table>


9.  (オプション) 外線を取得するのに、ユーザーが 1 つまたは複数の番号 (9 など) を先頭に追加してダイヤルする必要がある場合にのみ、\[**外部アクセス プレフィックス**\] フィールドに値を指定します。プレフィックス値には、最大 4 文字 (\#、\*、0 ～ 9) 入力できます。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>外部アクセス プレフィックスを指定した場合、プレフィックスに対応するのに、新しい正規化ルールを作成する必要はありません。</td>
    </tr>
    </tbody>
    </table>


10. 次の手順でダイヤル プランの正規化ルールを関連付けて構成します。
    
      - エンタープライズ VoIP 展開で使用可能なすべての正規化ルールの一覧から、1 つまたは複数のルールを選択するには、\[**選択**\] をクリックします。\[**正規化ルールの選択**\] で、ダイヤル プランに関連付けるルールをハイライトしてから、\[**OK**\] をクリックします。
    
      - 新しい正規化ルールを定義してダイヤル プランに関連付けるには、\[**新規**\] をクリックします。新しいルールの定義の詳細については、「[Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)」を参照してください。
    
      - 既にダイヤル プランに関連付けられている正規化ルールを編集するには、ルールの名前を選択状態にして \[**詳細の表示**\] をクリックします。ルールの編集の詳細については、「[Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)」を参照してください。
    
      - 既存の正規化ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前を選択状態にして \[**コピー**\] をクリックし、\[**貼り付け**\] をクリックします。コピーの編集の詳細については、「[Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)」を参照してください。
    
      - ダイヤル プランから正規化ルールを削除するには、ルールの名前を選択状態にして \[**削除**\] をクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>ダイヤル プランごとに少なくとも 1 つの関連付けられた正規化ルールが必要です。ダイヤル プランが必要とするすべての正規化ルールを設定する方法の詳細については、「計画」のドキュメントの「<a href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 のダイヤル プランと正規化ルール</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


11. ダイヤル プランの正規化ルールが、正しい順序で並んでいることを確認します。一覧内でのルールの位置を変更するには、ルールの名前を選択状態にして、上矢印または下矢印をクリックします。
    

    > [!IMPORTANT]
    > Lync Server は正規化ルールの一覧を上から順に検索し、ダイヤルされた番号と最初に一致するルールを使用します。ダイヤル プランを構成し、その結果ダイヤルされる番号が複数の正規化ルールと一致する可能性がある場合は、制限の厳しいルールが制限の緩いルールより上に並び替えてください。<BR>既定の [<STRONG>Keep All</STRONG>] (すべてを保持) 正規化ルール「<STRONG>^(\d{11})$</STRONG> 」は、任意の 11 桁の数字と一致します。たとえば、1425 ではじまる 11 桁の番号に一致する正規化ルールを追加した場合、[<STRONG>Keep All</STRONG>] が、より厳格な「<STRONG>^(1425\d{7})$</STRONG> 」ルールの下に配置されるようにします。



12. (オプション) ダイヤル プランをテストする番号を入力して、\[**実行**\] をクリックします。テスト結果が \[**テストする番号の入力**\] の下に表示されます。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>まだテストに成功していないダイヤル プランを保存して、後で再構成することができます。詳細については、「<a href="lync-server-2013-test-voice-routing.md">Lync Server 2013 での音声ルーティングのテスト</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


13. \[**OK**\] をクリックします。

14. \[**ダイヤル プラン**\] ページで \[**確定**\] をクリックして、\[**すべて確定**\] をクリックします。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>ダイヤル プランを作成したときはかならず、[<strong>すべて確定</strong>] コマンドを実行して構成の変更を公開する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開</a>」を参照してください。</td>
    </tr>
    </tbody>
    </table>


## 関連項目

#### タスク

[Lync Server 2013 でのダイヤル プランの変更](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### その他のリソース

[Lync Server 2013 の正規化ルールの定義](lync-server-2013-defining-normalization-rules.md)

