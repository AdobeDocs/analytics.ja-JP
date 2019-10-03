---
description: この統合の展開は、以下の操作を必要とする簡単なプロセスです。
seo-description: この統合の展開は、以下の操作を必要とする簡単なプロセスです。
seo-title: 統合のデプロイ
solution: Analytics
subtopic: Qualtrics
title: 統合のデプロイ
topic: Data Connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfef09
translation-type: tm+mt
source-git-commit: f326b29bb73fd6e8630957c43dfd89f47b711986

---


# 統合のデプロイ{#deploying-the-integration}

この統合の展開は、以下の操作を必要とする簡単なプロセスです。

## Adobe統合ウィザードの完了{#completing-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectorsインターフェイス内でQualtrics統合ウィザードを完了する必要があります

1. data connectorsに移動し、Qualtrics統合ウィザードを起動します。
1. この統合に使用するレポートスイートを選択し、名前を指定します。

   次の手順に従って、統合ウィザードを完了します。 1.ウィザ **ードの手順1**

   | Email Address | 主連絡先の電子メールアドレス。 |
   |---|---|
   | 説明 | （オプション）この統合設定の説明。 |
   | Qualtrics組織ID | [Qualtrics組織IDの検索](../qualtrics-overview/qualtrics-org-id.md) |
   | Adobe siteCatalystトークン | [Qualtrics Adobe Analyticsトークンの生成](../qualtrics-overview/qualtrics-token.md) |

1. **ウィザードの手順2 — 変数のマッピング**| Qualtrics応答リスト|使用可能なリスト変数をレポートスイートから選択します。 （場合によっては、Report Suite Manager内で新しいlistVarを有効にする必要があります）。||—|—|| Qualtrics応答ID|使用可能なeVarまたはpropをレポートスイートから選択します。 （場合によっては、Report Suite Manager内で新しいlistVarを有効にする必要があります）。||トラッキングサーバー|Adobe Analyticsデータの追跡に使用するトラッキングサーバー（ドメイン）設定を指定します。 標準のトラッキ `trackingServerSecure` ングサーバー設定と異なる場合は、トラッキングサーバーを使用します。  || Qualtrics調査の提出|レポートスイートから利用可能なイベントを選択します（Report Suite Manager内で新しいイベントを有効にする必要がある場合があります）。  |

1. **Wizard Step 3: Nothing required, informational only.**

   ステップ結果1 **Wizard Step 4 - Export Settings**

   | eVar | Qualtricsに書き出すeVarを5つまで選択できます。 |
   |---|---|
   | イベント | Select up to five of your custom events to expose for exporting to Qualtrics |
   | prop | Select up to five of your Props to expose for exporting to Qualtrics |
   | Access Requests | Check the box for any of the standard metrics and dimensions that you wish to export to Qualtrics. The  is required to allow the export to function properly.`visitor_id` |

1. **Wizard Step 5: Review configuration and then click Activate Now.******

## Enabling the Integration in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

After completing the integration wizard, you must activate the integration for each Qualtrics survey that you want connected.

1. Log in to the Qualtrics Research Suite.
1. 「マイ **[!UICONTROL 調査]** 」タブで、統合する **[!UICONTROL 調査の「編集]** 」ボタンをクリックします。
1. Click the Advanced Options menu and select Adobe Analytics. ********(if you do not see this option, ask your administrator about gaining the permissions required).

   ![](assets/advanced_options.png)

1. 「Adobe Analytics設定」を選択し、「保存」をクリッ **[!UICONTROL クします]**。 If no configurations are available then you likely have not yet completed the Adobe Integration Wizard.
   1. The Include Partial Responses checkbox can be used to indicate that you’d like to capture data into Adobe Analytics after each partial survey screen is completed. **** If not checked, then data is transferred only for fully completed surveys.
   1. 「Send Timestamp With Beacon **** 」チェックボックスは、タイムスタンプ付きのデータ（共通ではない）を受け取るように設定されたレポートスイートとの統合時にのみ使用します。
   ![](assets/integration_config.png)

## 統合の確認{#verifying-the-integration}

すべての導入手順が完了したら、統合が正常にデータを転送していることを検証できます。

1. **統合アクティビティログ**:Data Connectors UIで、Qualtrics統合の「 **[!UICONTROL Support]** 」タブを表示します。 「統合アクティビティログ **** 」の見出しの下に、分類データのインポートが成功したことを示すエントリが表示されます。

   >[!NOTE]
   >
   >これらのエントリは、展開が成功してから1時間以内に表示されます。

   ![](assets/verify-1.png)

1. **レポートデータ**:Qualtrics調査レポートをReports &amp; Analytics UIで表示するには、Qualtrics調査レポート(「リスト変数」の下 ****)に移動します。

   >[!NOTE]
   >
   >このデータは、統合調査が積極的に回答を受け取っていると仮定して、導入が成功してから24 ～ 48時間以内に表示されます。

   ![](assets/verify-2.png) ![](assets/verify-3.png)


