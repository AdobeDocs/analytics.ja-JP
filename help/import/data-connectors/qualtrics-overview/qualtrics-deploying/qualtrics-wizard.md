---
description: 統合をアクティブ化するには、Data Connectorsインターフェイス内のQualtrics統合ウィザードを完了する必要があります
seo-description: 統合をアクティブ化するには、Data Connectorsインターフェイス内のQualtrics統合ウィザードを完了する必要があります
seo-title: Adobe統合ウィザードの完了
solution: Analytics
subtopic: Qualtrics
title: Adobe統合ウィザードの完了
topic: Data Connectors
uuid: e065fba4-1fe1-4e25-9c45-6c52dc20f81e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Adobe統合ウィザードの完了{#completing-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectorsインターフェイス内のQualtrics統合ウィザードを完了する必要があります

1. data connectorsに移動し、Qualtrics統合ウィザードを起動します。([Data Connectors ヘルプ](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. この統合に使用するレポートスイートを選択し、名前を指定します。

   統合ウィザードを完了し、次の手順に従って情報を提供します。1. **ウィザードステップ1**

   | Email Address | プライマリ連絡先電子メールアドレス。 |
   |---|---|
   | 説明 | （オプション）この統合設定の説明。 |
   | Qualtrics組織ID | [Qualtrics組織IDの参照](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96) |
   | Adobe SiteCatalystトークン | [Qualtrics Adobe Analyticsトークンの生成](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372) |

1. **ウィザードステップ2-変数のマッピング**

   | Qualtrics応答リスト | 使用可能なリスト変数をレポートスイートから選択します。（Report Suite Manager内で新しいListVarを有効にする必要があります）。 |
   |---|---|
   | Qualtrics応答ID | 利用可能なeVarまたはpropをレポートスイートから選択します。（Report Suite Manager内で新しいListVarを有効にする必要があります）。 |
   | トラッキングサーバー | Adobe Analyticsデータの追跡に使用するトラッキングサーバー（ドメイン）設定を指定します。`trackingServerSecure` トラッキングサーバーは、標準トラッキングサーバー設定とは異なる場合に使用します。 |
   | Qualtrics調査の送信 | レポートスイートから使用可能なイベントを選択します（Report Suite Managerから新しいイベントを有効にする場合があります）。 |

1. **ウィザード手順3**:必要な情報は何もありません。情報のみ。

   手順1.**ウィザードステップ4-エクスポート設定**

   | eVar | QualtricsにエクスポートするためのeVarの最大5個を選択します |
   |---|---|
   | Events | Qualtricsにエクスポートするために公開するカスタムイベントの最大5つを選択します |
   | prop | Qualtricsへのエクスポートに使用できるpropの最大5つを選択します |
   | Access Requests | Qualtricsにエクスポートする標準指標およびディメンションのチェックボックスをオンにします。`visitor_id` エクスポートを正常に機能させるには、これが必要です。 |

1. **ウィザード手順5**:設定を確認し、「今すぐアクティブ化」をクリック ****&#x200B;します。
