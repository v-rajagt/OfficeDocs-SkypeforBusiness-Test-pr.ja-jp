﻿---
title: 'Lync Server 2013: カテゴリの構成'
TOCTitle: カテゴリの構成
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48271948
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのカテゴリの構成

 

_**トピックの最終更新日:** 2012-10-06_

Lync Server 2013 コントロール パネルの \[**常設チャット**\] ページの \[**カテゴリ**\] セクションを使用して、カテゴリを構成できます。常設チャット ルーム カテゴリは、チャット ルームを整理するための論理的な構造です。カテゴリでは、チャット ルームを作成したり、チャット ルームに参加したりできるユーザーおよびユーザー グループを制御するためのアクセス制御リスト (ACL) の既定のセットを定義します。カテゴリを使用して、組織内の異なる部門間に倫理的境界を設置することもできます。

チャット ルーム カテゴリには、チャット ルームのカテゴリのみを含めることができます。他のカテゴリは含めることができません。各カテゴリでは、*\[名前\]*、*\[説明\]* などのメタデータを使用してカテゴリの内容が記述されます。また、カテゴリには、チャット ルームで *\[招待\]* や *\[ファイル アップロード\]* が許可されるかどうか、チャット ルームに *\[チャットの履歴\]* が含まれるかどうかなど、そのカテゴリに属するチャット ルームの動作を制御するプロパティを設定できます。

## チャット ルームのカテゴリを構成するには

1.  CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  \[**スタート**\] メニューから \[ Lync Server コントロール パネル\] を選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。Lync Server コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。
    

    > [!IMPORTANT]
    > Windows PowerShell コマンドレットを使用することもできます。詳細については、「展開」のドキュメントの「<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成</A>」を参照してください。



3.  左側のナビゲーション バーで \[**常設チャット**\] をクリックして、\[**カテゴリ**\] をクリックします。
    
    複数の 常設チャット サーバー プールを展開する場合は、ドロップダウン リストから適切なプールを選択します。

4.  \[**Category**\] ページで、\[**New**\] または \[**Edit**\] をクリックします。

5.  \[**サービスの選択**\] で、カテゴリを作成する必要のある 常設チャット サーバー プールに対応するサービスを選択します。サービスは、カテゴリが属するプールを識別するために 常設チャット (クライアント) が使用する 常設チャット サーバー プールです。1 つのカテゴリは 1 つの 常設チャット サーバー プールにのみ属することができ、他のプールに移動したり、他のプールと共有したりできません。

6.  \[**New Category**\] で、次の操作を実行します。
    
    1.  \[**Name**\] に、新しいルーム カテゴリの名前を指定します。
    
    2.  \[**説明**\] に、ルーム カテゴリの詳細を指定します (たとえば「Contoso 用のカテゴリ」と指定します。)。
    
    3.  このカテゴリに属するチャット ルームに対して招待を有効にできるかどうかを制御するには、\[**招待状を有効にする**\] チェック ボックスをオンまたはオフにします。オンにした場合、このカテゴリのルームでは招待がオンまたはオフになります。オフにした場合、このカテゴリのルームでは招待は許可されません。ルームの招待がオンの場合、新しいメンバーがルームに追加されると、そのメンバーは 常設チャット クライアント内の新しいルームの通知を受け取ります。
    
    4.  このカテゴリに属するチャット ルームでファイルのアップロードを制御するには、\[**ファイルのアップロードを有効にする**\] チェック ボックスをオンまたはオフにします。オンにした場合、このカテゴリのルームでは、ファイルのアップロードを有効または無効にできます。オフにした場合、このカテゴリのルームではファイルのアップロードは許可されません。
        

        > [!IMPORTANT]
        > カスタム アプリケーション、あるいは Office Communications Server 2007 R2グループ チャット サーバー または Lync Server 2010、グループ チャット を使用する従来の グループ チャット クライアントはチャット ルームにファイルを投稿できるため、この設定がサーバーに対して適用されます。Lync 2013 クライアントにはファイル アップロード/ダウンロード機能がないため、純粋な Lync 2013 展開または Lync 2013 クライアントの場合は 常設チャット サーバー チャット ルームにファイルを投稿することはできません。

    
    5.  チャットの履歴を制御するには、\[**チャット履歴を有効にする**\] チェック ボックスをオンまたはオフにします。オンにした場合、ルームでのチャットは永続的になります。オフにした場合、チャット メッセージは保持されません。コンプライアンスが有効な場合、ルームでのチャットは保存されますが、ユーザーは古いメッセージにアクセスできません。このオプションは、チャット履歴を保存する必要のない、リアルタイムの一時的なコラボレーションを目的としたルームで使用できます。

7.  \[**Edit Category**\] で、次の操作を実行します。
    
      - \[**メンバーシップ**\] の \[**許可されたメンバー**\] セクションで、カテゴリに属するチャット ルームのメンバーとして追加が許可されるユーザーまたは他の Active Directory ドメイン サービス プリンシパル (ユーザー、配布グループ、組織単位など) を追加または削除します。カテゴリで許可されるプリンシパルは、カテゴリ内のルームを検索できます (ルームが非表示になっていない場合。ルームが非表示になっている場合は、ルームのメンバーのみがディレクトリ内のルームを検索できます)。
    
      - \[**メンバーシップ**\] の \[**拒否されたメンバー**\] セクションで、ルームで拒否されているメンバーに関連付けられたユーザーおよび他の Active Directory プリンシパルを追加または削除します。
    
      - \[**メンバーシップ**\] の \[**作成者**\] セクションで、カテゴリの作成者に関連付けられているユーザーおよび他の Active Directory プリンシパルを追加または削除します。作成者は、チャット ルームを作成し、チャット ルームのマネージャーとメンバーを割り当てることができるアクセス許可を持つユーザーです。

8.  \[**確定**\] をクリックします。
