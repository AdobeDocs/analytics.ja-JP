---
description: 必要な権限、利用可能なディメンションや指標など、Advertising Analyticsで実行できるあらゆることを確認してください。
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 10%

---

# Advertising Analytics

Advertising Analyticsでは、Adobe Analytics内で、Google AdsとMicrosoft Advertisingの有料検索データを並べて表示できます。 以前は、Google AdsまたはMicrosoft Advertisingのデータは、Adobe Advertisingまたは各広告インターフェイスで表示する必要がありました。 AMO ID インスタンス（クリックインスタンス）だけでなく、検索エンジンからインプレッション、クリック、コストのデータを直接取得できるようになりました。

Adobe Analyticsを使用して、それらの検索エンジンから収集したデータを統合し、Analysis Workspaceの機能を活用して分析できます。 Workspaceの新しい[有料検索パフォーマンス ](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) テンプレートがこの分析を容易にします。

![](assets/aa_aw.png)

この統合は、次のオーディエンスを対象としています。

* 有料検索マーケターのパフォーマンスレポートを収集する必要がある&#x200B;**アナリスト**&#x200B;です。
* これらの質問に対する回答を求める&#x200B;**有料検索マーケター**&#x200B;は、「サイトに送信するトラフィックの量とコンバージョン率は？」と質問しました。 費用対効果の高い広告キャンペーンとは？


## 前提条件 {#prerequisites}

* Advertising Analyticsは、Adobe Analytics [Select](https://www.adobe.com/jp/data-analytics-cloud/analytics/select.html)、[Prime](https://www.adobe.com/jp/data-analytics-cloud/analytics/prime.html)、および[Ultimate](https://www.adobe.com/jp/data-analytics-cloud/analytics/ultimate.html) SKUでのみ使用できます。
* この機能は、Adobe Advertisingを使用していないお客様が使用できます。
* Advertising Analyticsへのアクセス権を持つAdobe Analytics管理者であるか、Advertising Analyticsへのアクセス権が[付与された製品プロファイル ](/help/integrate/c-advertising-analytics/overview.md#permissions)に属している必要があります。
* Google AdsまたはMicrosoft Advertisingの検索データを表示するレポートスイートの場合は、[Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)のレポートスイートを有効にする必要があります（**[!UICONTROL 管理者]** > **[!UICONTROL 設定を編集]** > **[!UICONTROL Advertising Analytics設定]**）。
* Google アカウント IDやパスワードなど、Adobe Analyticsと統合する検索アカウントに対する編集権限を持つユーザーのログイン資格情報が必要です。
* Microsoft Advertisingの場合は、[[!UICONTROL Account ID]および[!UICONTROL Manager Account ID]](c-adanalytics-workflow/aa-locate-account-id.md)も必要です。

## Advertising Analytics の権限 {#permissions}

Analyticsには、Analytics管理者に自動的に付与される2つの権限があります。 次に、管理者はこれらの権限を管理者以外のユーザーに付与することを選択できます。

| 権限 | 定義 | Adobe Experience Cloudにログインしている場合は、権限を付与します |
| --- | --- | --- |
| Advertising Analytics 管理 | ユーザーは広告検索アカウントを設定/編集/表示できます。 | [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] tab > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Management]にログインします |
| Advertising Analytics 設定 | Advertising Analytics用にプロビジョニングするレポートスイートをユーザーが設定できます。 | [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] tab > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Configuration]にログインします |

## Advertising Analyticsのディメンションと指標 {#dimensions-metrics}

Advertising Analyticsでは、Analysis Workspace、Report Builder、およびAnalytics レポート APIに次のディメンションと指標が追加されます。

### ディメンション

>[!IMPORTANT]
>
>この統合では、AMO ID 変数の分類によって新しいディメンションセットが作成されます。これらの新しいディメンションは、既存のマーケティングチャネルやキャンペーントラッキング変数のディメンションに影響を与えたり、変更したりすることはありません。 AMO IDは、訪問者が検索連動型広告からサイトにアクセスしたときに、訪問者のプロファイルに接続されます。 そのため、AMO ディメンションを使用すると、この統合によって提供されるAMO指標と、訪問者がダウンストリームで取り込んだデータ（訪問、訪問者、ページビュー、直帰率、注文、収益、カスタムイベントなど）の両方を分析できます。 また、他のオンサイト指標でレポートを作成する際に、他のディメンションで分類することもできます。
>
>これらの指標の分類は毎日更新されます。 そのため、検索エンジンのメタデータに変更を加えた場合、分類が更新された翌日まで、その変更が反映されない場合があります。

| 分類（ディメンション）名 | 定義 |
| --- | --- |
| **[!UICONTROL キーワード MatchType （AMO ID）]** | キーワード一致タイプ。 広告タイプに一致するタイプがない場合、通常、値はbroad、phrase、exact、またはnoのいずれかになります。 |
| **[!UICONTROL 広告プラットフォーム （AMO ID）]** | 検索エンジン名。 値には、「Google AdWords」または「Microsoft Bing Ads」を含めることができます。 |
| **[!UICONTROL アカウント （AMO ID）]** | 追跡される検索エンジンアカウントの名前。 |
| **[!UICONTROL キャンペーン （AMO ID）]** | 検索エンジンアカウント内のキャンペーンの名前。 |
| **[!UICONTROL 広告グループ （AMO ID）]** | 検索エンジンキャンペーン内の広告グループの名前。 |
| **[!UICONTROL 広告（AMO ID）]** | 広告で使用される広告タイトル +広告説明。 |
| **[!UICONTROL キーワード （AMO ID）]** | 検索エンジンアカウントのキーワード値。 |
| **[!UICONTROL 一致タイプ （AMO ID）]** | キーワードに割り当てられたキーワード一致タイプ。通常、値は部分一致、フレーズ一致、完全一致となり、広告タイプに一致するタイプがない場合は値なしです。 |
| **[!UICONTROL 広告タイプ （AMO ID）]** | 提供される広告のタイプ。通常は「テキスト広告」です。 |
| **[!UICONTROL 広告タイトル （AMO ID）]** | 広告で使用されるタイトルオブジェクト。 |
| **[!UICONTROL 広告の説明（AMO ID）]** | 広告で使用される広告説明オブジェクト。 |
| **[!UICONTROL 広告の表示URL （AMO ID）]** | 広告で使用される広告表示URL オブジェクト。 |
| **[!UICONTROL 広告宛先URL （AMO ID）]** | 広告に割り当てられたランディングページ URLまたは最終URL。 |
| **[!UICONTROL ネットワーク （AMO ID）]** | 広告が配信されるネットワーク。 Advertising Analytics では、この値は常に「Search」です。 |
| **[!UICONTROL 配置（AMO ID）]** | 管理されている配置の Web サイト（コンテンツネットワーク向け）。このディメンションを使用するのは、管理されたプレースメントのみです。 |
| **[!UICONTROL 製品ターゲット （AMO ID）]** | PLA広告で使用される製品ターゲットの名前（実際に購入した製品ではありません）。 |
| **[!UICONTROL 最適化（AMO ID）]** | Advertising Analyticsでは使用されません。 Adobe Advertisingのお客様のみが使用できます。 |
| **[!UICONTROL デバイス （AMO ID）]** | 現在使われていません。 広告のターゲットデバイスタイプ（モバイル、デスクトップなど）に対する潜在的な製品の機能強化のプレースホルダー（実際の訪問者デバイスではない）。 |

### 指標

>[!IMPORTANT]
>
>Advertising Analytics で利用できる指標（以下の一覧を参照）は、検索エンジンからのサマリレベルのデータです。これらはAnalytics訪問者プロファイルに接続されていません。 これらは、AMO ID変数とそれに関連付けられた分類ディメンションにのみ接続されます。 そのため、AMO ID ディメンションに基づくディメンション/セグメント以外のディメンション/セグメントで報告しないでください。 そうすると、Analyticsにデータの0が表示されます。 他の指標と計算指標に含めることもできますが、これらの計算指標はAMO ID ディメンションによってのみ分類する必要があります。
>
>これらの指標は毎日データを取得しているため、現在のデータは保持されません。 また、日次よりも細かく報告すべきではありません。
>
>AMO IDがランディングページ（クリックスルー）で設定されたときに設定されるAMO ID インスタンス指標があります。 この指標は、ランディングページがヒットした際にリアルタイムで取得され、ランディングページに設定されている他のディメンションを使用して分類できます。

| Metric name | 定義 |
| --- | --- |
| **[!UICONTROL AMO インプレッション]** | 検索エンジンによって報告された広告インプレッションの数。 |
| **[!UICONTROL AMO クリック数]** | 検索エンジンによって報告された広告のクリック数。 |
| **[!UICONTROL AMO コスト]** | 検索エンジンによって報告された、各キーワード/広告に対して支払われたコスト。 |
