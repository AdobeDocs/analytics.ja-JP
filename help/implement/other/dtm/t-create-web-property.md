---
description: Web プロパティは、1 つ以上のドメインおよびサブドメインの集合と複数のルールで構成され、1 つの埋め込みコードに組み込まれます。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Web プロパティの作成
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Web プロパティの作成

Web プロパティは、1 つ以上のドメインおよびサブドメインの集合と複数のルールで構成され、1 つの埋め込みコードに組み込まれます。

>[!NOTE]プロパティを作成できるのは管理者権限を持つユーザーのみです。ロールについて詳しくは、『Dynamic Tag Management 製品ドキュメント』の [DTM のグループの作成と管理](https://marketing.adobe.com/resources/help/ja_JP/dtm/groups.html)を参照してください。

DTMを使用して、これらのアセットを管理および追跡できます。 例えば、1つのテンプレートに基づく複数のWebサイトがあり、これらすべてのWebサイトの同じアセットを追跡するとします。 1つのWebプロパティを複数のドメインに適用できます。

Web プロパティの概要とベストプラクティスについては、Dynamic Tag Management 製品ドキュメントの [Web プロパティ](https://marketing.adobe.com/resources/help/ja_JP/dtm/web_property.html)を参照してください。

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
    <td colname="col1"> <span class="uicontrol">名前</span> </td> 
    <td colname="col2"> <p>プロパティの名前。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>プロパティのベース URL。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol">複数のドメインを計測する</span> </td> 
    <td colname="col2"> <p>ドメインデータをドメイン間で保持する場合は、訪問者を追加および削除できます。 このオプションを選択した場合、訪問のデータはサブドメイン間で保持されます。 </p> <p>この設定を使用すると、関連するサブドメインまたはドメイン間を移動するトラフィックを追跡する方法を指定できます。 サブドメインへのリンクは、アウトバウンドリンクとして扱われます。 サブドメインへの訪問は別々に追跡されます。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. （オプション）設定を参照してくだ [!UICONTROL Advanced Settings]さい。

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
    <td colname="col2"> <p>このプロパティの複数のルールを 1 度に承認することを許可しますデフォルトの承認では、単一ルールの承認のみが許可されます。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 一部のみの発行を可能にする</span> </td> 
    <td colname="col2"> <p>承認されたルールの発行先をユーザーが選択できるようにするかどうかを指定します。 これはデフォルトのオプションです。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol">Cookie 名のトラッキング</span> </td> 
    <td colname="col2"> <p>デフォルトのトラッキング Cookie 名より優先されます。Dynamic Tag Managementが他のcookieを受け取る際のオプトアウトステータスを追跡する際に使用する名前をカスタマイズできます。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> タグのタイムアウト</span> </td> 
    <td colname="col2"> <p>Dynamic Tag Managementがタグの起動を待ってから、タグのリクエストをタイムアウトしてキャンセルするまでの時間を指定します。 </p> <p> Dynamic Tag Managementの仕組み上、この数が多いことは気にしないでください。 DTMには、タグの速度を遅くしてもユーザーエクスペリエンスに影響を与えない効果的な方法があります。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> リンクの遅延</span> </td> 
    <td colname="col2"> <p>クリックされたリンクでタグが実行されてから次のページに移動するまでの時間を、Dynamic Tag Managementが待機する時間を指定します。 デフォルト値は 100 ミリ秒です。 </p> <p>この時間を長くするとトラッキングの精度が向上します。アドビでは、ユーザーに遅延を意識させないよう 500 ミリ秒以下の設定値を推奨しています。 </p> <p>Dynamic Tag Managementは指定された時間まで待機しますが、ビーコンが早く起動した場合は遅延が短くなります。 （つまり、ユーザーの待ち時間は必ずしもこの設定値ほど長くはなりません）。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. クリック **[!UICONTROL Create Property]**.
