﻿---
title: 監視ダッシュボードの使用
TOCTitle: 監視ダッシュボードの使用
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49887176
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 監視ダッシュボードの使用

 

_**トピックの最終更新日:** 2014-02-05_

監視ダッシュボードは、管理者に Microsoft Lync Server 2013 システムの状態と使用状況の概要を提供します。このダッシュボードは、主要なシステム指標の集計ビューを表示するように設計されており、次のいずれかを表示します。

  - 現在の日付に対する合計。現在の日付に対して表示される値は、夜中 12 時から現在の時刻 (レポート サーバーのローカル時刻に基づく) までに記録されたデーターを表すことに注意してください。つまり、通常は、24 時間ではなく、特定の日付のデータが表示されます。たとえば、サーバーのローカル時刻が午前 8 時の場合、深夜 12 時から現在の時刻の午前 8 時の間には 8 時間あるので、8 時間分のデータが表示されます。

  - 週に対する合計と過去 6 週間の傾向の合計。

  - 月に対する合計と過去 6 か月の傾向の合計 (システム使用状況のみ)。

[Get-CsReportingConfiguration](get-csreportingconfiguration.md) コマンドレットを使うと、Lync Server 2013 の監視レポートにアクセスするための URL に戻れます。

    Get-CsReportingConfiguration

既定では、監視ダッシュボードは、現在の週に対する次の指標 (および過去 6 週間の傾向の合計) を表示します。

## システム使用状況の指標

**登録**

  - 一意のユーザー ログオン

**ピアツーピア**

  - セッションの合計数

  - IM セッション

  - オーディオ セッション

  - ビデオ セッション

  - アプリケーション共有

  - オーディオ セッションの合計時間 (分)

  - オーディオ セッションの平均時間 (分)

**会議**

  - 会議の合計数

  - IM 会議

  - 音声ビデオ会議

  - アプリケーション共有会議

  - Web 会議

  - 開催者の合計数

  - 音声ビデオ会議の合計時間 (分)

  - 音声ビデオ会議の平均時間 (分)

  - PSTN 会議の合計数

  - PSTN 参加者の合計数

  - PSTN 参加者の合計時間 (分)

システム使用状況の指標に加えて、次の指標では、現在の日付および過去 6 日間に対する合計 (\[**週ビュー**\] を選択した場合)、または現在の週および過去 6 週間に対する合計 (\[**月ビュー**\] を選択した場合) が表示されます。

## ユーザーごとの通話診断

**通話でエラーが発生したユーザー**

  - 通話でエラーが発生したユーザーの合計数

  - 通話でエラーが発生した会議開催者

**通話が低品質なユーザー**

  - 通話が低品質なユーザーの合計数

## 通話診断

ピアツーピア

  - エラーの合計数

  - 全体的なエラー率

  - IM エラー率

  - 音声エラー率

  - アプリケーション共有エラー率

会議

  - エラーの合計数

  - 全体的なエラー率

  - IM エラー率

  - 音声ビデオ エラー率

  - アプリケーション共有エラー率

セッションのエラー率が高い上位 5 台のサーバー

## メディア品質診断

ピアツーピア

  - 低品質通話の合計数

  - 低品質通話のパーセンテージ

  - 低品質な PSTN 通話

会議

  - 低品質通話の合計数

  - 低品質通話のパーセンテージ

  - 低品質な PSTN 通話

低品質通話のパーセンテージが高い上位 5 台のサーバー

## 監視ダッシュボードの操作

既に説明したように、既定では、現在の週に対する合計と過去 6 週間の傾向値が表示されます。現在の月に対する合計 (および過去 6 か月の傾向値) を表示する場合は、ダッシュボードの右上隅にある \[**月ビュー**リンクをクリックします。月に対する合計の表示を決定すると、リンク テキストが \[**週ビュー**\] に変わります。そのリンクをクリックすると、週ビューに再び切り替わります。


> [!TIP]
> 監視ダッシュボードでは、現在の週 (または現在の月) に対する合計と過去 6 週間 (または過去 6 か月) の傾向値を表示するように制限されています。これらの日時を変更することはできません。たとえば、ダッシュボードを使用して、9 か月前から始まる期間に対するレポート合計を表示することはできません。



\[**今週**\]、\[**今月**\]、または \[**今日**\] 列に表示される値は、アイテムに関する詳細情報にリンクされています。その列に表示される列名と値は、選択した指標、および週ビューまたは月ビューのどちらを選択したかに応じて異なることに注意してください。たとえば、\[**一意のユーザー ログオン**\] 指標に対して表示される合計をクリックした場合は、指定した期間に対する \[**ユーザー登録レポート**\] が表示されます。\[**ダッシュボード**\] をクリックすると、監視ダッシュボードにいつでも戻ることができます。


> [!TIP]
> ダッシュボードの右上隅にある [<STRONG>レポート</STRONG>] リンクをクリックして、監視サーバー レポートのホーム ページにアクセスすることもできます。



\[**傾向**\] 列には、過去 6 週間 (または、指標および時間間隔に応じて、過去 6 日間または過去 6 か月) に対する合計を表す簡単な折れ線グラフが表示されます。これらの簡単な折れ線グラフは、各期間に対する 1 つの未分類のデータ点 (たとえば、それぞれの過去 6 週間に対する 1 つの未分類のデータ点) を表示します。ただし、マウス ポインタをグラフ上に合わせることにより、これらのグラフの実際の値を取得できます。この場合、グラフの最大値と最小値がツール ヒントに表示されます。

## 監視ダッシュボードからのデータ エクスポート

監視ダッシュボードは、現在のダッシュボード ビューをエクスポートするさまざまな方法を備えています。ダッシュボードのツールバーには、緑の矢印が付いたフロッピー ディスクのように見えるアイコンがあります。このアイコンをクリックすると、次のデータ エクスポート形式がリストされたドロップダウン リストが表示されます。

  - レポート データが含まれている XML ファイル

  - CSV (コンマ区切り)

  - PDF

  - MHTML (Web アーカイブ)

  - Excel

  - TIFF ファイル

  - Word

現在のダッシュボード ビュー (およびその値) をエクスポートするには、目的のエクスポート オプションをクリックします。Lync Server 2013 により、レポートが指定した形式で生成され、そのレポートを開くオプションまたは保存するオプションが表示されます。Lync Server では、既定でレポートに \[**監視ダッシュボード**\] というタイトルが付けられ、レポートがダッシュボード フォルダーに保存されることに注意してください。レポートに別の名前を付ける場合、またはレポートを異なるフォルダーに保存する場合は、\[**保存**\] ボタンの隣にある矢印をクリックし、\[**名前を付けて保存**\] をクリックします。レポートを \[**監視ダッシュボード**\] という名前でダッシュボード フォルダーに保存しても問題ない場合は、\[**保存**\] ボタンをクリックします。

ダッシュボード データのエクスポートを試みたとき、\[**セキュリティの警告**\] ダイアログ ボックスと「現在のセキュリティ設定では、このファイルをダウンロードできません。」というメッセージが表示される可能性があります。このダイアログ ボックスとメッセージが表示された場合は、次の操作を実行してください。

  - Internet Explorer で、\[**インターネット オプション**\] をクリックします。

  - \[**インターネット オプション**\] ダイアログ ボックスの \[**セキュリティ**\] タブで、\[**信頼済みサイト**\] をクリックし、\[**サイト**\] をクリックします。

  - \[**信頼済みサイト**\] ダイアログ ボックスで、\[**追加**\] をクリックし、Lync Server 2013 レポートを実行している Lync Server 2013 を信頼済み Web サイトのコレクションに追加します。

  - \[**閉じる**\] をクリックし、\[**OK**\] をクリックします。

次に、変更が反映される前に、監視ダッシュボードを更新する必要があります。監視ダッシュボードを更新するには、F5 を押すか、ダッシュボードのツールバーにある \[**更新**\] アイコンをクリックします (\[**更新**\] アイコンは緑の矢印のペアを囲んだ丸いアイコンです)。

最新の監視ダッシュボード データへのリンクがあるライブ データ フィードが含まれた Excel スプレッドシートを作成することもできます。ライブ データ フィードのファイルを作成するには、ツールバーにあるオレンジ色の \[**データ フィードへのエクスポート**\] アイコンをクリックします。

現在のダッシュボードを印刷する場合は、ツールバーにあるプリンター アイコンをクリックします。

