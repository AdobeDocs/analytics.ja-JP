---
description: この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。
subtopic: Qualtrics
title: 統合のデプロイ
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 98%

---


# 統合のデプロイ {#deploying-the-integration}

この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。

## アドビ統合ウィザードの完了 {#completing-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectors インターフェイス内で Qualtrics 統合ウィザードを完了する必要があります。

1. Data Connectors に移動し、Qualtrics 統合ウィザードを起動します。
1. この統合に使用するレポートスイートを選択し、名前を指定します。

   次の手順に従って情報を入力し、統合ウィザードを完了します。1. **ウィザード：手順 1**

   | 電子メールアドレス | 主要連絡先の電子メールアドレス。 |
   |---|---|
   | 説明 | （オプション）この統合設定の説明。 |
   | Qualtrics 組織 ID | [Qualtrics 組織 ID の検索](../qualtrics-overview/qualtrics-org-id.md) |
   | Adobe SiteCatalyst トークン | [Qualtrics Adobe Analytics トークンの生成](../qualtrics-overview/qualtrics-token.md) |

1. **ウィザードの手順 2 - 変数のマッピング**| Qualtrics 応答リスト | 使用可能なリスト変数をレポートスイートから選択します。（場合によっては、Report Suite Manager 内で新しい listVar を有効にする必要があります）|
|---|---|
| Qualtrics 応答 ID | レポートスイート尾から使用可能な eVar または prop を選択します。（場合によっては、Report Suite Manager 内で新しい listVar を有効にする必要があります）|
| トラッキングサーバー | Adobe Analytics データの追跡に使用するトラッキングサーバー（ドメイン）設定。その場合は、 
`trackingServerSecure` トラッキングサーバーを設定します。|| Qualtrics 調査の提出 | レポートスイートから利用可能なイベントを選択します（Report Suite Manager 内で新しいイベントの有効化が必要になる場合があります）。|

1. **ウィザード：手順 3**：何もする必要はありません。情報のみ。

   手順の結果 1 **ウィザードの手順 4 - 設定の書き出し**

   | eVar | Qualtrics に書き出す eVar を 5 つまで選択します。 |
   |---|---|
   | イベント | Qualtrics に書き出すカスタムイベントを 5 つまで選択します。 |
   | Props | Qualtrics に書き出す Props を 5 つまで選択します。 |
   | アクセス要求 | Qualtrics に書き出す標準指標および標準ディメンションのチェックボックスをオンにします。書き出しが正しく機能するには、`visitor_id` が必要です。 |

1. **ウィザード：手順 5**：設定を確認し、「**[!UICONTROL 今すぐアクティブ化]**」をクリックします。

## Qualtrics Research Suite での統合の有効化 {#enabling-the-integration-in-qualtrics-research-suite}

統合ウィザードを完了したら、結び付けをおこなう各 Qualtrics 調査の統合をアクティブ化する必要があります。

1. Qualtrics Research Suite にログインします。
1. 「**[!UICONTROL マイ調査]**」タブで、統合する調査の「**[!UICONTROL 編集]**」ボタンをクリックします。
1. **[!UICONTROL アドバンスオプション]**&#x200B;メニューをクリックし、「**[!UICONTROL Adobe Analytics]**」を選択します。（このオプションが表示されない場合は、必要な権限の取得について管理者に問い合わせてください）

   ![](assets/advanced_options.png)

1. 「Adobe Analytics 設定」を選択し、「**[!UICONTROL 保存]**」をクリックします。使用できる設定がない場合は、アドビ統合ウィザードを完了していない可能性があります。
   1. 「**[!UICONTROL 部分的な回答を含む]**」チェックボックスを使用すると、部分的な調査の各画面が完了した後で Adobe Analytics にデータを取り込むことを示すことができます。選択しない場合、完全に完了した調査のデータのみが転送されます。
   1. 「**[!UICONTROL ビーコンとともにタイムスタンプを送信]**」チェックボックスは、タイムスタンプ付きのデータ（共通ではない）を受け取るように設定されたレポートスイートとの統合時にのみ使用してください。

   ![](assets/integration_config.png)

## 統合の確認 {#verifying-the-integration}

すべての実装手順が完了したら、統合が正常にデータを転送していることを検証できます。

1. **統合アクティビティログ**：Data Connectors UI で、Qualtrics 統合の「**[!UICONTROL サポート]**」タブを表示します。「**[!UICONTROL 統合アクティビティログ]**」の見出しの下に、分類データの読み込みが成功したことを示すエントリが表示されます。

   >[!NOTE]
   >
   >これらのエントリは、デプロイメントが成功してから 1 時間以内に表示されます。

   ![](assets/verify-1.png)

1. **レポートデータ**：Qualtrics 調査レポートを Marketing Reports and Analytics UI で表示するには、Qualtrics 調査レポート（「**[!UICONTROL リスト変数]**」の下）に移動します。

   >[!NOTE]
   >
   >このデータは、統合調査が積極的に回答を受け取っていると想定して、デプロイメントが成功してから 24 ～ 48 時間以内に表示されます。

   ![](assets/verify-2.png) ![](assets/verify-3.png)


