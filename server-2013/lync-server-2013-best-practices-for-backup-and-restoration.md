﻿---
title: バックアップと復元のベスト プラクティス
TOCTitle: バックアップと復元のベスト プラクティス
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202184(v=OCS.15)
ms:contentKeyID: 52056675
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# バックアップと復元のベスト プラクティス

 

_**トピックの最終更新日:** 2013-02-21_

このセクションでは、次の 2 種類のベスト プラクティスを説明します。

  - バックアップと復元のベスト プラクティス

  - 障害の影響を最小限に抑えるベスト プラクティス

## バックアップと復元のベスト プラクティス

バックアップと復元のプロセスを円滑に行えるようにするために、データのバックアップと復元を行うとき次のベスト プラクティスを適用してください。

  - 定期的なバックアップを適切な間隔で遂行する。一番簡単で、特によく使われるバックアップの種類とローテーションのスケジュールは、SQL Server データベース全体を夜間に毎日完全バックアップするというものです。こうしておけば、復元が必要になっても、復元プロセスで 1 つのバックアップしか必要にならず、1 日分以上のデータが失われることはありません。

  - コマンドレットまたは Lync Server コントロール パネルで構成変更を行う場合、データベースの復元が必要になったときにその変更を失いたくなければ、変更後に **Export-CsConfiguration** コマンドレットでトポロジ構成ファイル (Xds.mdf) のスナップショット バックアップをとっておく。この構成は XML 形式でバックアップされ、ZIP ファイルに圧縮されます。

  - Lync Server のバックアップに使う予定の共有フォルダーに、すべてのバックアップ データを収容する十分なディスク スペースがあることを確認する。

  - サーバー パフォーマンスとユーザー エクスペリエンスを向上するために、Lync Server の使用率が低い時間帯を見計らってバックアップする。

  - データのバックアップ先が安全であることを確認する (リモートの場所をお勧めします)。

  - データの復元に備えてバックアップ ファイルをいつでも利用できるようにしておく。

  - 組織でサポートされている復元プロセスの定期的なテストを計画して、予定どおり実施する。

  - バックアップと復元のプロセスが期待どおりうまくいくことを確かめる前に、その妥当性を確認する。

## 障害の影響を最小限に抑えるベスト プラクティス

障害によるサービスの中断 (停電、突然のハードウェア故障などの制御しがたい事態によって引き起こされる) に対処する最善の戦略は、それが当然起こるものと考えて、それ相応の計画を立てることです。バックアップと復元の戦略の一環として練り上げる障害管理計画に、以下のプラクティスを含めてください。

Lync サービスの停止と中断の発生が最小であることが組織のビジネスにとって重要な場合は、「[Lync Server 2013 での高可用性および障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明するように、 相互にペアとなるフロントエンド サーバーの実装を検討する必要があります。このプールのどちらかに障害が発生した場合、管理者はそのプールのユーザーを他のプールに切り替えることができるため、ダウンタイムを最小限に抑えられます。

バックアップと復元の戦略の一環として練り上げる障害管理計画に、以下のプラクティスを含めてください。

  - ソフトウェア メディアとソフトウェアおよびファームウェアの更新プログラムをいつでも利用できるようにしておく。

  - ハードウェアおよびソフトウェアに関する記録を残しておく。

  - データを定期的にバックアップし、バックアップの整合性を監視する。

  - 障害回復のスタッフを訓練し、手順を文書化し、障害回復シミュレーション演習を実施する。

  - 予備のハードウェアをいつでも利用できるようにしておく。サービス レベル契約 (SLA) を結ぶ場合は、ハードウェア ベンダーや納入業者と即時交換の契約をする。

  - トランザクション ログ ファイル (.ldf ファイル) とデータベース ファイル (.mdf ファイル) を別の場所に保存する。

