﻿---
title: 'Lync Server 2013: 監視レポートの使用'
TOCTitle: 監視レポートの使用
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48272454
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での監視レポートの使用

 

_**トピックの最終更新日:** 2012-10-21_

Lync Server 2013 には、Microsoft SQL Server Reporting Services によって公開された一連の標準レポートが格納されています。これらのレポートには、Web ブラウザーを使用してアクセスでき、使用状況、通話診断情報、およびメディア品質情報が示されます。これらの情報はすべて、通話詳細記録 (CDR) および Quality of Experience (QoE) データベースに格納されている CDR および QoE データに基づいて提供されます。

これらのレポートを使用するには、SQL Server のインスタンスを実行しているコンピューターに監視レポートをインストールする必要があります。

## このセクション中

  - [監視ダッシュボードの使用](lync-server-2013-using-the-monitoring-dashboard.md)   システムの正常性および使用状況に関する概要を管理者に提供します。

  - [Lync Server 2013 のシステム使用状況レポート](lync-server-2013-system-usage-reports.md)    Lync Server によって収集された CDR データに基づいてシステムの使用状況に関する情報を提供します。

  - [Lync Server 2013 の通話診断レポート (ユーザーごと)](lync-server-2013-call-diagnostic-reports-per-user.md)   エラーが発生したピアツーピア セッションと電話会議セッションに関する情報をユーザー別に提供します。

  - [Lync Server 2013 の通話診断レポート](lync-server-2013-call-diagnostic-reports.md)   エラーが発生したピアツーピア セッションと電話会議セッションに関する概要情報と診断データを提供します。

  - [Lync Server 2013 のメディア品質診断レポート](lync-server-2013-media-quality-diagnostic-reports.md)   通話品質に関する情報のほか、エラーが発生した通話の診断およびトラブルシューティングに関する情報を提供します。

## レコードの検索

監視レポートで画面上に一度に表示されるレコードの数は限られています。実際に画面に表示されるレコードの数は、レポートによって異なります。画面に現在表示されていないレコードを表示する場合は、データの表示ページを切り替えることができる標準の "進む" および "戻る" のコントロール (各レポートのツール バー上にあります) を使用できます。また、データセットの最初または最後のページにすばやく移動できます。

"進む" と "戻る" のコントロールを使用する以外に、\[**現在のページ**\] ボックスにページ番号を入力して Enter キーを押すだけで、データセットの任意のページに移動することもできます。

各レポートには、データの表示ページを切り替える機能だけでなく、制限付きのレコード検索の機能も用意されています。特定の値に基づいてレコードを検索するには、その値を \[**検索**\] ボックスに入力し、\[**検索**\] をクリックします。レポートでデータの検索が開始され、\[**検索**\] ボックスに入力した値の最初のインスタンスが見つかると検索は停止します。検索基準を満たす次のレコードを探すには、\[**次へ**\] をクリックします。

前述のとおり、監視レポートには非常に基本的な検索機能しかありません。たとえば、どのフィールドで値を検索するのかは指定できません。この検索メカニズムでは、自動的にすべてのレコードのすべてのフィールドを対象にして一致する値の検索が行われます。また、検索にワイルドカードは使用できず、すべての検索は値の部分一致に基づいて行われます。つまり、"111" を検索した場合は、111 という値だけでなく、11100、811、3112、611A5B といった値や、フィールド内のどこかに "111" が含まれるその他すべてのフィールドも返されます。

各レポートは、既定のレコード セットを表示するように構成されています。たとえば、既定のユーザー登録レポートでは、この 1 週間のユーザー登録アクティビティが表示されます。場合によっては、レポートによってレコードが 1 つも返されないことがあります。これは、ユーザー登録がこの 1 週間に一度も行われなかったということです。"レポート フィルターに一致する結果はありません" というメッセージが表示された場合は、フィルターの値を変更 (たとえば、検索対象の期間を過去 1 週間から過去 1 か月に変更) して、クエリを再実行します。詳細については、後のセクション「データのフィルター処理」を参照してください。

## データのフィルター処理

レコードのサブセットのみの検索が必要になることもあります (たとえば、ピアツーピア セッションと会議セッションの両方ではなく、ピアツーピア セッションのみの検索など)。同様に、結果として返されるレコード数の削減が必要になることもあります。既定では、1 つのレポートで表示できる対象がデータ セット内の最初の 1,000 レコードまでに制限されています。こうした問題に対処するために、ほとんどのレポートにはいくつかのフィルター オプションが用意されています。たとえば、2011 年 1 月 1 日から 2011 年 1 月 15 日までの期間のレコードのみを表示する場合は、\[**開始**\] ボックスに「2011 年 1 月 1 日」、\[**終了**\] ボックスに「2011 年 1 月 15 日」と入力できます。続いて、\[**レポートの表示**\] をクリックすると、返されるデータが 2011 年 1 月 1 日から 2011 年 1 月 15 日までに発生したアクティビティのみに制限されます。

使用できるフィルターは、表示しているレポートによって異なります。特定のレポートの詳細については、レポートのヘルプ トピックを参照してください。

## データのエクスポート

監視レポートには、レポート内のデータをエクスポートする方法が少なくとも 2 つあります。各レポートの最上部に表示されるツール バーの \[**エクスポート**\] オプションを使用することです。このオプションを使用するには、\[**形式を選択してください**\] ドロップダウン リストで適切なエクスポート形式を選択します。使用できる形式は次のとおりです。

  - レポート データが含まれている XML ファイル

  - CSV (コンマ区切り)

  - Acrobat (PDF) ファイル

  - MHTML (Web アーカイブ)

  - Excel

  - TIFF ファイル

  - Word

形式の選択後、\[**エクスポート**\] をクリックします。\[**ファイルのダウンロード**\] ダイアログ ボックスが表示されたら、\[**保存**\] をクリックします。\[ **名前を付けて保存**\] ダイアログ ボックスで、保存先フォルダーを選択し、ファイル名を入力して、\[**保存**\] をクリックします。

Microsoft OneNote がインストールされている場合は、レポート データを OneNote にコピーすることもできます。そのためには、ツールバーの \[**レポートの表示**\] ボタンをクリックします。\[**OneNote の場所の選択**\] ダイアログ ボックスで、データのコピー先となる OneNote のセクションを選択し、\[**OK**\] をクリックします。
