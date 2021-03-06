﻿---
title: Lync Server 2013 での会議ポリシー設定の参照
TOCTitle: Lync Server 2013 での会議ポリシー設定の参照
ms:assetid: ec8125f7-ef78-4a2b-8db0-4dd3cf5a4065
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg429724(v=OCS.15)
ms:contentKeyID: 48273932
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での会議ポリシー設定の参照

 

_**トピックの最終更新日:** 2014-04-22_

このトピックの各表に、Lync Server 2013 コントロール パネル を使用して指定できるすべての会議ポリシー設定の一覧を示します。

## 開催者ポリシー設定

以下の表に、会議の開催者に適用可能なすべての会議ポリシー設定の一覧を示します。会議ポリシー設定の最新の一覧については、[Set-CsClientPolicy](set-csclientpolicy.md) コマンドレットのヘルプ トピックをご覧ください。

### 開催者ポリシー設定

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>設定</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最大会議サイズ</p></td>
<td><p>ミーティングに参加可能な最大人数を設定します。</p></td>
</tr>
<tr class="even">
<td><p>参加者に匿名ユーザーの招待を許可する</p></td>
<td><p>会議の開催者に未認証ユーザーをミーティングに招待することを許可します。</p></td>
</tr>
<tr class="odd">
<td><p>レコーディングを有効にする</p></td>
<td><p>発表者または出席者にミーティングのレコーディングを許可します。</p></td>
</tr>
<tr class="even">
<td><p>フェデレーション参加者と匿名参加者にレコーディングを許可する</p></td>
<td><p>外部および未認証の参加者にミーティングのレコーディングを許可します。</p></td>
</tr>
<tr class="odd">
<td><p>[IP オーディオを有効にする]</p></td>
<td><p>ミーティングでのオーディオの使用を許可します。</p></td>
</tr>
<tr class="even">
<td><p>IP オーディオ/ビデオを有効にする</p></td>
<td><p>ミーティングでのオーディオおよびビデオの使用を許可します。</p></td>
</tr>
<tr class="odd">
<td><p>PSTN ダイヤルイン会議を有効にする</p></td>
<td><p>ユーザーに公衆交換電話網 (PSTN) からダイヤルインしてミーティングに出席することを許可します。</p></td>
</tr>
<tr class="even">
<td><p>匿名参加者にダイヤルアウトを許可する</p></td>
<td><p>未認証ユーザーにダイヤルアウト番号を使用してミーティングに参加することを許可します。 会議サーバーはダイヤルアウト番号を使用してユーザーを呼び出し、ユーザーはその電話に応答し会議に参加します。</p></td>
</tr>
<tr class="odd">
<td><p>会議でのビデオの最大解像度</p></td>
<td><p>ビデオ会議の最大解像度を設定します。 有効な値は、[<strong>640*480(VGA)</strong>] と [<strong>352*288(CIF)</strong>] です。</p></td>
</tr>
<tr class="even">
<td><p>共同作業データを有効にする</p></td>
<td><p>共同作業データ会議または Web 会議を有効にします。</p></td>
</tr>
<tr class="odd">
<td><p>フェデレーション参加者と匿名参加者にコンテンツのダウンロードを許可する</p></td>
<td><p>外部および未認証の参加者に会議のコンテンツをダウンロードすることを許可します。</p></td>
</tr>
<tr class="even">
<td><p>参加者にファイルの転送を許可する</p></td>
<td><p>ミーティング中にファイルを転送することをミーティング参加者に許可します。</p></td>
</tr>
<tr class="odd">
<td><p>注釈を有効にする</p></td>
<td><p>コンテンツに注釈を付けることをミーティング参加者に許可します。</p></td>
</tr>
<tr class="even">
<td><p>投票を有効にする</p></td>
<td><p>ミーティング中に投票を行うことをミーティング参加者に許可します。</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有を有効にする</p></td>
<td><p>ユーザーにアプリケーション共有をサポートするミーティングをスケジュールすることを許可します。</p></td>
</tr>
<tr class="even">
<td><p>参加者にコントロールを許可する</p></td>
<td><p>参加者に別のユーザーの共有アプリケーションのコントロールを許可します。</p></td>
</tr>
<tr class="odd">
<td><p>フェデレーション参加者と匿名参加者にコントロールを許可する</p></td>
<td><p>外部および匿名の参加者に別のユーザーの共有アプリケーションのコントロールを許可します。</p>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>この設定を True にし、[<strong>参加者にコントロールを許可する</strong>] を False に設定する場合、この設定は無視されます。</td>
</tr>
</tbody>
</table>

</div></td>
</tr>
</tbody>
</table>


## 参加者ポリシー設定

以下の表に、会議の参加者に適用可能なすべての会議ポリシー設定の一覧を示します。

### 参加者ポリシー設定

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>設定</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>アプリケーション共有を有効にする</p></td>
<td><p>ユーザーにアプリケーション共有をサポートするミーティングをスケジュールすることを許可します。</p></td>
</tr>
<tr class="even">
<td><p>アプリケーションとデスクトップの共有を有効にする</p></td>
<td><p>ユーザーにアプリケーション共有とデスクトップ共有をサポートするミーティングに参加することを許可します。会議では、会議の開催者に適用されるこの設定の値が、共に参加する匿名のエンドポイントすべてに適用されます。</p></td>
</tr>
<tr class="odd">
<td><p>ピアツーピア ファイル転送を有効にする</p></td>
<td><p>ミーティング中にピアツーピア ファイル転送を実行することを参加者に許可します。 ピアツーピア ファイル転送に関係するのは、ミーティング参加者のすべてではありません。</p></td>
</tr>
<tr class="even">
<td><p>ピアツーピアのレコーディングを有効にする</p></td>
<td><p>参加者にピアツーピア会議セッションのレコーディングを許可します。</p></td>
</tr>
</tbody>
</table>

