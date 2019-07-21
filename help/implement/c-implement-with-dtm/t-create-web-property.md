---
description: Web プロパティは、1 つ以上のドメインおよびサブドメインの集合と複数のルールで構成され、1 つの埋め込みコードに組み込まれます。
keywords: Analyticsの導入;導入方法、Dynamic Tag Management;dtm;webプロパティ;property
seo-description: Web プロパティは、1 つ以上のドメインおよびサブドメインの集合と複数のルールで構成され、1 つの埋め込みコードに組み込まれます。
seo-title: Webプロパティを作成
solution: Analytics
title: Webプロパティを作成
topic: 開発者と導入
uuid: f19d5504- eb44-4d93- a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Webプロパティを作成

Web プロパティは、1 つ以上のドメインおよびサブドメインの集合と複数のルールで構成され、1 つの埋め込みコードに組み込まれます。

>[!NOTE]
>
>管理者権限を持つユーザーのみがプロパティを作成できます。For more information about roles, see [Create and Manage Groups in DTM](https://marketing.adobe.com/resources/help/en_US/dtm/groups.html) in the Dynamic Tag Management Product Documentation.

それらのアセットを DTM で管理および追跡できます。例えば、1 つのテンプレートに基づく複数の Web サイトがあり、それらすべての Web サイトに関する共通のアセットを追跡する場合などに役立ちます。1 つの Web プロパティを複数のドメインに適用することもできます。

Web プロパティの概要とベストプラクティスについては、「[Dynamic Tag Management製品ドキュメント](https://marketing.adobe.com/resources/help/en_US/dtm/web_property.html) のWebプロパティを参照してください。

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

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
    <td colname="col1"> <span class="uicontrol"> Name</span> </td> 
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
    <td colname="col1"> <span class="uicontrol"> DTM 用 Cookie 名</span> </td> 
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

1. Click **[!UICONTROL Create Property]**.
