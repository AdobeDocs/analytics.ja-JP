---
description: 必要な権限、使用可能なディメンションや指標など、Advertising Analyticsで実行できるすべての操作について説明します。
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 70%

---

# Advertising Analytics

Advertising Analyticsを使用すると、すべてのGoogle Ads とMicrosoft Advertisingの有料検索データをAdobe Analytics内に並べて表示できます。 以前は、Google広告またはMicrosoft Advertisingのデータは、Adobe Advertising Cloud （AMO）または各広告インターフェイスで表示する必要がありました。 インプレッション、クリックおよびコストデータを、検索エンジンと AMO ID インスタンス（クリックインスタンス）から直接取得できるようになりました。

これらの検索エンジンからデータをまとめて Adobe Analytics に取り込むことで、Analysis Workspace の高い機能性を利用して同じデータを分析できます。Workspaceの新しい [ 有料検索パフォーマンス ](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) テンプレートにより、この分析を容易におこなうことができます。

![](assets/aa_aw.png)

この統合は、以下のオーディエンスを対象にしています。

* 有料検索マーケターのパフォーマンスレポートを収集する必要がある&#x200B;**アナリスト**。
* 次の問いの答えを模索している&#x200B;**有料検索マーケター**：自社サイトへ自分で送信しているトラフィックの量、お客様が変換しているトラフィックの量はどの程度か。コスト効果の高い広告キャンペーンとはどのようなものか。


## 前提条件 {#prerequisites}

* Advertising Analytics は、Adobe Analytics [Select](https://www.adobe.com/jp/data-analytics-cloud/analytics/select.html)、[Prime](https://www.adobe.com/jp/data-analytics-cloud/analytics/prime.html)、[Ultimate](https://www.adobe.com/jp/data-analytics-cloud/analytics/ultimate.html) SKU でのみ利用できます。
* この機能は、Advertising Cloud 以外、および AMO 以外のお客様が利用できます。
* Advertising Analyticsへのアクセス権を持つには、Adobe Analytics管理者であるか、Advertising Analyticsへのアクセス権が [ 付与 ](/help/integrate/c-advertising-analytics/overview.md#permissions) されている製品プロファイルに属している必要があります。
* Google Ads またはMicrosoft Advertisingの検索データを表示する任意のレポートスイートについて、[Advertising Analyticsのレポートスイートを有効にする ](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) （**[!UICONTROL 管理者]**/**[!UICONTROL 設定を編集]**/6}Advertising Analytics Configuration **[!UICONTROL ）必要があります。]**
* Adobe Analytics と統合するアカウントを検索するには、編集権限を持つユーザーのログイン資格情報（Google アカウント ID とパスワードなど）が必要です。
* Microsoft Advertisingの場合は、[[!UICONTROL  アカウント ID] と [!UICONTROL  管理者アカウント ID]](c-adanalytics-workflow/aa-locate-account-id.md) も必要です。

## Advertising Analytics の権限 {#permissions}

Analytics には、Analytics 管理者に自動的に付与される 2 つの権限があります。 管理者は、これらの権限を管理者以外のユーザーに付与することを選択できます。

| 権限 | 定義 | Adobe Experience Cloud にログインしている場合の権限の付与 |
| --- | --- | --- |
| Advertising Analytics 管理 | ユーザーは Advertising 検索アカウントを設定／編集／表示できます。 | [adminconsole.adobe.com](https://adminconsole.adobe.com)/[!UICONTROL Products]/4}Adobe Analytics[!UICONTROL /]Product Profile[!UICONTROL /]Permissions[!UICONTROL  タブ/]Analytics Tools[!UICONTROL /12}Advertising Analytics Management] にログインします。 |
| Advertising Analytics 設定 | ユーザーは、Advertising Analytics 用にプロビジョニングするレポートスイートを設定できます。 | [adminconsole.adobe.com](https://adminconsole.adobe.com)/[!UICONTROL Products]/4}Adobe Analytics[!UICONTROL /]Product Profile[!UICONTROL /]Permissions[!UICONTROL  タブ/]Analytics Tools[!UICONTROL /12}Advertising Analytics Configuration] にログインします。 |

## Advertising Analyticsのディメンションと指標 {#dimensions-metrics}

Advertising Analyticsは、次のディメンションと指標をAnalysis Workspace、Report Builderおよび Analytics レポート API に追加します。

### ディメンション

>[!IMPORTANT]
>
>この統合では、AMO ID 変数の分類によって新しいディメンションセットが作成されます。この新しいディメンションは、既存のマーケティングチャネルまたはキャンペーンのトラッキング変数ディメンションには影響せず、それらを変更しません。AMO ID は、訪問者が有料検索広告からサイトにランディングしたときに、訪問者のプロファイルに接続されます。このように、AMO ディメンションを使用して、この統合によってもたらされる AMO 指標と、訪問者によってダウンストリームでキャプチャされるデータの両方の内訳を表示できます（訪問回数、訪問者数、ページビュー数、バウンス率、注文件数、売上高、カスタムイベントなど）。これらの内訳は、他のオンサイト指標のレポート時に他のディメンションによっても表示できます。
>
>これらの指標の分類は毎日更新されます。このため、検索エンジンのメタデータに変更を加えた場合、それらの変更が反映されるのを翌日分類が更新されるまで認識できない可能性があります。

| 分類（ディメンション）名 | 定義 |
| --- | --- |
| **[!UICONTROL キーワード MatchType （AMO ID）]** | キーワード一致タイプ。通常、値は部分一致、フレーズ一致、完全一致となり、広告タイプに一致するタイプがない場合は値なしです。 |
| **[!UICONTROL 広告プラットフォーム （AMO ID）]** | 検索エンジンの名前。値には、「Google AdWords」や「Microsoft Bing Ads」を含めることができます。 |
| **[!UICONTROL アカウント （AMO ID）]** | トラッキングする検索エンジンアカウントの名前。 |
| **[!UICONTROL キャンペーン （AMO ID）]** | 検索エンジンアカウントでのキャンペーン名。 |
| **[!UICONTROL 広告グループ （AMO ID）]** | 検索エンジンキャンペーンでの広告グループ名。 |
| **[!UICONTROL 広告（AMO ID）]** | 広告で使用される広告タイトル + 広告の説明。 |
| **[!UICONTROL キーワード （AMO ID）]** | 検索エンジンアカウントからのキーワード値。 |
| **[!UICONTROL 一致するタイプ （AMO ID）]** | キーワードに割り当てられたキーワードの一致タイプ。通常、値は部分一致、フレーズ一致、完全一致となり、広告タイプに一致するタイプがない場合は値なしです。 |
| **[!UICONTROL 広告タイプ （AMO ID）]** | 提供される広告のタイプ。通常は「テキスト広告」です。 |
| **[!UICONTROL 広告タイトル （AMO ID）]** | 広告で使用されるタイトルオブジェクト。 |
| **[!UICONTROL 広告説明（AMO ID）]** | 広告で使用される広告の説明オブジェクト。 |
| **[!UICONTROL 広告ディスプレイ URL （AMO ID）]** | 広告で使用される広告のディスプレイ URL オブジェクト。 |
| **[!UICONTROL 広告宛先 URL （AMO ID）]** | 広告に割り当てられたランディングページの URL または最終 URL。 |
| **[!UICONTROL ネットワーク （AMO ID）]** | 広告が掲載されているネットワーク。Advertising Analytics では、この値は常に「Search」です。 |
| **[!UICONTROL プレースメント （AMO ID）]** | 管理されている配置の Web サイト（コンテンツネットワーク向け）。このディメンションは管理されているプレースメントのみによって使用されます。 |
| **[!UICONTROL 製品ターゲット （AMO ID）]** | PLA 広告で使用される製品の名前（購入した実際の製品ではありません）。 |
| **[!UICONTROL 最適化（AMO ID）]** | Advertising Analytics では使用しません。Advertising Cloud のお客様のみが使用します。 |
| **[!UICONTROL デバイス （AMO ID）]** | 現在は使用しません。広告のターゲットのデバイスタイプ（モバイル、デスクトップなど）を示すための、将来の潜在的な製品の改良用のプレースホルダーです（訪問者の実際のデバイスではありません）。 |

### 指標

>[!IMPORTANT]
>
>Advertising Analytics で利用できる指標（以下の一覧を参照）は、検索エンジンからのサマリレベルのデータです。これらは Analytics の訪問者プロファイルには接続されません。AMO ID 変数とそれに関連する分類ディメンションのみに接続されます。このため、これらは AMO ID ディメンションに基づくもの以外のディメンション／セグメントによってレポートされません。レポートすると Analytics ではデータがゼロで表示されます。これらの指標は、他の指標とともに計算指標に含めることができますが、その計算指標の内訳は AMO ID ディメンションでのみ表示されます。
>
>これらの指標は毎日取得されるデータなので、今日に対応するデータはなくなります。また「毎日」より低い精度でレポートすることはできません。
>
>AMO ID がランディングページに設定されると設定される、AMO ID インスタンス指標があります（クリックスルーなど）。この指標は、ランディングページヒットによってリアルタイムにキャプチャされ、同じランディングページに設定されている他のディメンションとともに内訳を示すために使用できます。

| Metric name | 定義 |
| --- | --- |
| **[!UICONTROL AMO インプレッション数]** | 検索エンジンでレポートされる広告インプレッション数。 |
| **[!UICONTROL AMO クリック数]** | 検索エンジンでレポートされる広告のクリック数。 |
| **[!UICONTROL AMO コスト]** | 検索エンジンでレポートされる、キーワード／広告ごとに支払われたコスト。 |
