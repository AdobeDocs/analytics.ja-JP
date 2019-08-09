---
description: Silverpop用のData Connectors統合では、Analytics変数を使用して様々なSilverpop指標を追跡します。
seo-description: Silverpop用のData Connectors統合では、Analytics変数を使用して様々なSilverpop指標を追跡します。
seo-title: Analytics統合変数
title: Analytics統合変数
uuid: 3aef3cabf- e24e-4fe7- b4d7-50ca0f6703b5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

Silverpop用のData Connectors統合では、Analytics変数を使用して様々なSilverpop指標を追跡します。

Silverpop統合で使用するイベントとeVarを識別したら、Adobe Analytics管理コンソールを使用して有効にします（ [レポートスイート](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=report_suites_admin)を参照）。

次の表に、Silverpop統合に必要なAnalytics変数を示します。

## 必須の変数 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 変数の種類 | 名前 | セット方法 | 説明 |
|---|---|---|---|
| event（数値） | バウンス | Silverpopから自動的にインポートされます。 | バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 |
| event（数値） | Clicks | Silverpopから自動的にインポートされます。 | クリックイベントにより、電子メールメッセージをクリックした訪問者の数を確認できます。 |
| event（数値） | 開封数 | Silverpopから自動的にインポートされます。 | 開封イベントでは、電子メールメッセージを開いた訪問者の数を確認できます。 |
| event（数値） | 送信数 | Silverpopから自動的にインポートされます。 | Sendイベントを使用すると、送信された電子メールメッセージの数を確認できます。 |
| event（数値） | サブスクライブ解除 | Silverpopから自動的にインポートされます。 | 登録解除イベントにより、電子メールメッセージを開いたが、組織からの将来の電子メールメッセージをオプトアウトするためのリンク解除リンクをクリックした訪問者の数を確認できます。 |
| eVar | Silverpop ID/Visitor ID | 自動収集方法またはJavaScriptプラグインを介して電子メールリンクのクエリパラメーターから収集されます。 | 個別訪問者ID |
| eVarまたはs. campaign | メールID | 自動収集方法またはJavaScriptプラグインを介して電子メールリンクのクエリパラメーターから収集されます。 | これは多くの場合、キャンペーン変数に格納されます。 |

## オプションの変数 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 変数の種類 | 名前 | セット方法 | 説明 |
|---|---|---|---|
| イベント（カウンター） | ファイルのダウンロード | Analyticsタグを使用して手動で収集します。 | このイベントは、サイト上のファイルをダウンロードしたユーザーを識別するために使用します。 |
| イベント（カウンター） | フォーム開始 | Analyticsタグを使用して手動で収集します。 | 「フォームを開始」は、フォームを開始したが完了しないユーザーを識別するために使用されます。 |
| イベント（カウンター） | フォーム完了 | Analyticsタグを使用して手動で収集します。 | フォーム完了は、フォームを開始して完了しない訪問者を識別するために使用します。 |
| eVar | Email Address | Analyticsタグを使用して手動で収集します。 | 電子メールアドレスは、電子メールアドレスが収集されたサインイン、ログインまたはその他のページの電子メールアドレスを手動で収集するためのものです。この変数は、電子メールの受信に同意しているが、過去に電子メールをクリックスルーしていないユーザーに再マーケティングするために使用されます。 |
| eVar | ダウンロードしたファイル | Analyticsタグを使用して手動で収集します。 | ダウンロードしたファイルは、訪問者がどのファイルをダウンロードしたかを識別します。 |
| eVar | フォーム名 | Analyticsタグを使用して手動で収集します。 | フォーム名は、訪問者が放棄したフォームを識別します。 |

