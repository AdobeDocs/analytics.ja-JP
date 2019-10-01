---
description: Silverpop用のData Connectors統合では、Analytics変数を使用して様々なSilverpop指標を追跡します。
seo-description: Silverpop用のData Connectors統合では、Analytics変数を使用して様々なSilverpop指標を追跡します。
seo-title: Analytics統合変数
title: Analytics統合変数
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analytics Integration Variables{#analytics-integration-variables}

Silverpop用のData Connectors統合では、Analytics変数を使用して様々なSilverpop指標を追跡します。

Silverpop統合で使用するイベントとeVarを特定したら、Adobe Analytics管理コンソールを使用してそれらを有効にします(レポートスイート [を参照](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html))。

次の表に、Silverpop統合に必要なAnalytics変数を示します。

## 必須変数 {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| 変数の種類 | 名前 | セット方法 | 説明 |
|---|---|---|---|
| event（数値） | バウンス | Silverpopから自動的に読み込まれます。 | バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 |
| event（数値） | Clicks | Silverpopから自動的に読み込まれます。 | クリック済みイベントを使用すると、電子メールメッセージをクリックした訪問者の数を確認できます。 |
| event（数値） | 開封数 | Silverpopから自動的に読み込まれます。 | Openedイベントを使用すると、電子メールメッセージを開いた訪問者の数を確認できます。 |
| event（数値） | 送信数 | Silverpopから自動的に読み込まれます。 | Sendsイベントを使用すると、送信された電子メールメッセージの数を確認できます。 |
| event（数値） | 購読解除 | Silverpopから自動的に読み込まれます。 | 「購読解除」イベントを使用すると、電子メールメッセージを開いた訪問者の数を確認し、「購読解除」リンクをクリックして、組織からの今後の電子メールメッセージをオプトアウトできます。 |
| eVar | Silverpop ID/訪問者ID | 自動収集方法またはJavaScriptプラグインを使用して、電子メールリンクのクエリパラメーターから収集されます。 | 個別訪問者ID |
| eVarまたはs.campaign | 郵送ID | 自動収集方法またはJavaScriptプラグインを使用して、電子メールリンクのクエリパラメーターから収集されます。 | これは、多くの場合キャンペーン変数に保存されます。 |

## オプションの変数 {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| 変数の種類 | 名前 | セット方法 | 説明 |
|---|---|---|---|
| イベント（カウンター） | ファイルのダウンロード | Analyticsタグを使用して手動で収集されます。 | このイベントは、サイトにファイルをダウンロードしたユーザーを識別するために使用されます。 |
| イベント（カウンター） | フォーム開始 | Analyticsタグを使用して手動で収集されます。 | 「フォーム開始」は、フォームを開始したが完了しなかったユーザーを識別するために使用します。 |
| イベント（カウンター） | フォーム完了 | Analyticsタグを使用して手動で収集されます。 | フォーム完了は、フォームを開始し、完了しない訪問者を識別するために使用します。 |
| eVar | Email Address | Analyticsタグを使用して手動で収集されます。 | 「電子メールアドレス」は、電子メールアドレスを収集するページ、ログインページ、またはその他のページで、電子メールアドレスを手動で収集するためのものです。 この変数は、電子メールの受信をオプトインしたが、以前に電子メールをクリックしなかった可能性のあるユーザーに対して再マーケティングするために使用します。 |
| eVar | ダウンロード済みファイル | Analyticsタグを使用して手動で収集されます。 | ダウンロードされたファイルは、訪問者がダウンロードしたファイルを識別します。 |
| eVar | フォーム名 | Analyticsタグを使用して手動で収集されます。 | 「フォーム名」は、訪問者が破棄したフォームを識別します。 |

