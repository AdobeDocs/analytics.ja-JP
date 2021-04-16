---
description: Web プロパティは、1 つ以上のドメインおよびサブドメインの集合と複数のルールで構成され、1 つの埋め込みコードに組み込まれます。
keywords: Analytics の実装, 実装方法, dynamic tag management, dtm, web プロパティ, プロパティ
title: Web プロパティの作成
topic-fix: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
exl-id: f89381d0-bdf7-4e01-96a3-2ea160da2b44
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 100%

---

# Web プロパティの作成

Web プロパティは、1 つ以上のドメインおよびサブドメインの集合と複数のルールで構成され、1 つの埋め込みコードに組み込まれます。

>[!NOTE]
>
>プロパティを作成できるのは管理者権限を持つユーザーのみです。ロールについて詳しくは、『Dynamic Tag Management 製品ドキュメント』の [DTM のグループの作成と管理](https://docs.adobe.com/content/help/ja-JP/dtm/using/admin/groups.html)を参照してください。

それらのアセットを DTM で管理および追跡できます。例えば、1 つのテンプレートに基づく複数の Web サイトがあり、それらすべての Web サイトに関する共通のアセットを追跡する場合などに役立ちます。1 つの Web プロパティを複数のドメインに適用することもできます。

Web プロパティの概要とベストプラクティスについては、Dynamic Tag Management 製品ドキュメントの [Web プロパティ](https://docs.adobe.com/content/help/ja-JP/dtm/using/admin/web-property.html)を参照してください。

1. 会社ページに移動して、「**[!UICONTROL プロパティの追加]**」をクリックします。

   ![](assets/dtm-create-web-property.png)

1. 以下のフィールドを設定します。

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 要素 </th> 
    <th colname="col2" class="entry"> 説明 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol">名前</span> </td> 
    <td colname="col2"> <p>プロパティの名前。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>プロパティのベース URL。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol">複数のドメインを計測する</span> </td> 
    <td colname="col2"> <p>複数のドメインを視野に入れた訪問者データ永続化をおこなう場合、ドメインを追加することや削除することができます。このオプションを選択した場合、サブドメイン全体で訪問データが永続化されます。 </p> <p>この設定を使用すると、関連するサブドメインやドメインの間で移動するトラフィックをトラッキングする方法を指定できます。サブドメインへのリンクは、外部リンクとして扱われます。サブドメインへの訪問は、個別にトラッキングされます。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. （オプション）[!UICONTROL 詳細設定]を設定します。

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 要素 </th> 
    <th colname="col2" class="entry"> 説明 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 複数ルールの同時承認を可能にする</span> </td> 
    <td colname="col2"> <p>このプロパティの複数のルールを 1 度に承認することを許可しますデフォルトでは、1 つのルールの承認のみ可能です。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 一部のみの発行を可能にする</span> </td> 
    <td colname="col2"> <p>発行する承認済みのルールをユーザーが選択できるようにするかどうかを指定します。これがデフォルトのオプションです。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol">Cookie 名のトラッキング</span> </td> 
    <td colname="col2"> <p>デフォルトのトラッキング Cookie 名より優先されます。Dynamic Tag Management が別の Cookie の受信のオプトアウトステータスをトラッキングするために使用する名前をカスタマイズできます。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> タグのタイムアウト</span> </td> 
    <td colname="col2"> <p>タイムアウトし、タグリクエストをキャンセルするまでに Dynamic Tag Management がタグの起動を待つ時間を指定します。 </p> <p> Dynamic Tag Management の仕組み上、この数値を大きくしても問題ありません。DTM には、タグの処理速度が低下してもユーザーエクスペリエンスが影響を受けないよう効果的な対策が施されています。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> リンクの遅延</span> </td> 
    <td colname="col2"> <p>リンクがクリックされてから次のページに移動するまでの間に Dynamic Tag Management がタグの起動を待つ時間を指定します。デフォルト値は 100 ミリ秒です。 </p> <p>この時間を長くするとトラッキングの精度が向上します。アドビでは、ユーザーに遅延を意識させないよう 500 ミリ秒以下の設定値を推奨しています。 </p> <p>この値は Dynamic Tag Management が待機する時間の上限値であり、ビーコンが早く起動した場合には遅延が短くなります（つまり、ユーザーの待ち時間は必ずしもこの設定値ほど長くはなりません）。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 「**[!UICONTROL プロパティを作成]**」をクリックします。
