﻿---
title: 'Lync Server 2013: 組織の外部アクセス ポリシーの管理'
TOCTitle: 組織の外部アクセス ポリシーの管理
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48272128
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での組織の外部アクセス ポリシーの管理

 

_**トピックの最終更新日:** 2013-10-07_

1 つ以上の エッジ サーバーを展開したら、組織でサポートする各種外部ユーザー アクセスを有効にする必要があります。

組織で外部ユーザー アクセス (リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど) のサポートを既に有効にしていても、既定では外部ユーザー アクセスをサポートするように構成されているポリシーはありません。外部ユーザー アクセスの使用を制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。ポリシーの作成および構成時に使用できるスコープを次に示します。既定では、グローバル ポリシーが作成されますが、このポリシーを削除することはできません。

  - **グローバル ポリシー**   エッジ サーバーの展開時に作成されます。既定では、グローバル ポリシーで有効になっている外部ユーザー アクセス オプションはありません。外部ユーザー アクセスをグローバル レベルでサポートするには、1 種類以上の外部ユーザー アクセス オプションをサポートするようにグローバル ポリシーを構成します。グローバル ポリシーは組織のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーはグローバル ポリシーよりも優先されます。グローバル ポリシーを削除しても、ポリシー自体が削除されるのではなく、既定の設定にリセットされます。

  - **サイト ポリシー**   外部ユーザー アクセスのサポートを特定のサイトに限定するために、1 つ以上のサイト ポリシーを作成し、構成できます。サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定できます。既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てることで、サイト ポリシーの設定を無効にすることができます。

  - **ユーザー ポリシー**   リモート ユーザー アクセスのサポートを特定のユーザーに限定するために、1 つ以上のユーザー ポリシーを作成し、構成できます。ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーだけが対象となります。たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスを有効にしても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定し、そのポリシーを特定のユーザーに割り当てることができます。ユーザー ポリシーを作成した場合、ポリシーを有効にするには、1 人以上のユーザーに適用する必要があります。


> [!IMPORTANT]
> あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。



これらのオプションには、次の種類の外部アクセスが含まれます。

  - \[**フェデレーション ユーザーとの通信を有効にする**\]   フェデレーション パートナーのドメインへのユーザー アクセスをサポートする場合は、このオプションを有効にします。この設定により、ユーザーは他の SIP フェデレーション ドメインや、Microsoft Office 365 などのホストされるプロバイダーと通信できるようになります。この設定を選択すると、XMPP フェデレーション ドメインとの通信を可能にするオプションを選択できるようになります。
    
    \[**フェデレーション ユーザーとの通信を有効にする**\] を選択していれば、必要に応じて、\[**XMPP フェデレーション ユーザーとの通信を有効にする**\] を選択できます。XMPP フェデレーションは、Extensible Messaging and Presence Protocol (XMPP) を使用する組織とのフェデレーションです。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>XMPP フェデレーションを有効にした場合は、トポロジ ビルダーの エッジ プール構成セクションで、<strong>XMPP フェデレーション</strong>の展開も選択する必要があります。XMPP フェデレーションを構成すると、エッジ サーバーに XMPP プロキシ、フロント エンド サーバーに XMPP ゲートウェイが展開されます。</td>
    </tr>
    </tbody>
    </table>


  - \[**リモート ユーザーとの通信を有効にする**\]   ファイアウォールの外側にいる組織内のユーザー (在宅勤務者や出張中のユーザーなど) がインターネット経由で Lync Server に接続できるようにする場合は、このオプションを有効にします。

  - \[**パブリック ユーザーとの通信を有効にする**\]   内部ユーザーがパブリック IM プロバイダーの連絡先 ( Windows Live、Yahoo\!、および America Online (AOL) によって提供される連絡先など) と通信できるようにする場合は、このオプションを有効にします。
    

    > [!IMPORTANT]
    > <UL>
    > <LI>
    > <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳細については、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」を参照してください。</P>
    > <LI>
    > <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
    > <LI>
    > <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



<table>
<thead>
<tr class="header">
<th><img src="images/Gg412781.note(OCS.15).gif" title="note" alt="note" />注:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>外部ユーザー アクセスのサポートを有効にするだけでなく、ユーザーが任意の種類の外部ユーザー アクセスを使用できるようにする前に、組織内での外部ユーザー アクセスの使用を制御するポリシーも構成する必要があります。外部ユーザー アクセスのポリシーの作成、構成、および適用の詳細については、「<a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</a>」を参照してください。</td>
</tr>
</tbody>
</table>


**Windows PowerShell コマンドレットを使用して外部アクセス ポリシーを表示するには**

  - Lync Server 管理シェルと **Get-CsExternalAccessPolicy** コマンドレットを使用して、外部アクセス ポリシーを表示できます。このコマンドレットは、Lync Server 2013 管理シェルから実行することも、Windows PowerShell のリモート セッションから実行することもできます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。
    
    すべての外部アクセス ポリシーの情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
        Get-CsExternalAccessPolicy
    
    このコマンドは、次のような情報を返します。
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

## このセクション中

  - [Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [Lync Server 2013 外部ユーザー アクセス ポリシーのリセットまたは削除](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

