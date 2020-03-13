---
description: 'null'
title: データレイヤーオブジェクトをデータ要素にマップ
uuid: null
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# データレイヤーオブジェクトをデータ要素にマップ


実装用 [のデータレイヤーを作成し](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) 、その中のオブジェクトを起動のデータ要素 [にマップすることができます](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element)。 データ要素は、データマップの構成要素で、複数の方法で使用できます。 データ要素を使用して、Analyticsレポートを含むAdobe Platformソリューション全体でデータを収集、整理および配信できます。

データ・レイヤー・オブジェクトをLaunchデータ要素にマップするには：

1. 「起動」で、データ要素を追加するプロパティの名前をクリックします。 プロパティをまだ設定していない場合は、「起動プロパティを作成する」の手 [順を参照してください](https://docs.adobe.com/content/help/en/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch.html)。

2. Click **Data Elements** and then click **Create New Data Element**.

   ![データ要素を作成する](assets/createelement.png)


3. データ要素の名前を入力します。 この名前は、追跡するデータ層のJavaScript変数に対応する単純なラベルにする必要があります。

4. [拡張子]で、[コア]を選 **択します。** この拡張機能には、必要なすべての変数が含まれます。

5. For **Data Element Type**, select **JavaScript Variable**. 該当するフ **ィールドに** JavaScript変数名を入力します。 これは、JavaScriptデータレイヤー内のオブジェクトの名前と完全に一致する必要があります。

6. 「デフ **ォルト値**」に、デフォルトで設定する値を入力するか、必要に応じて空白のままにします。

7. 慣行に従って、小文字の値を強制的に入力するオプションを選択し、テキストをクリーンにする（「起動」では通常の間隔が適用されます）ことができます。

8. 新しいデータ要素の起動ストア値を設定する期間を指定します。

9. 「**保存**」をクリックします。

次の例は、起動のページ名データ要素で、データレイヤー内のJavaScript変数用に作 ``pageName`` 成されたものを示しています。

![要素を指定](assets/new_element.png)


データレイヤーオブジェクトをデータ要素にマッピングすると、それらを利用してAnalytics変数を設定できます。 詳しくは、データ要素のAnalytics [変数へのマッピングを参照してください](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)。
