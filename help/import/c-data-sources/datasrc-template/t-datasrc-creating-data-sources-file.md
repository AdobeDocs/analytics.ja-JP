---
description: インポートテンプレートファイルの目的は、インポートを開始できるようにすることです。
seo-description: インポートテンプレートファイルの目的は、インポートを開始できるようにすることです。
seo-title: インポートファイルテンプレートの生成
solution: Analytics
subtopic: データソース
title: インポートファイルテンプレートの生成
topic: 開発者と導入
uuid: bcd90e34-42e6-4cd1- b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# インポートファイルテンプレートの生成

インポートテンプレートファイルの目的は、インポートを開始できるようにすることです。

使用できる列はテンプレートで定義されているものに限られません。含める指標やディメンションが選択した処理タイプでサポートされている限り、必要に応じて列を追加することができます。各タイプでサポートされる指標やディメンションは、[Webログ](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)、 [トラフィック](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC)、 [コンバージョン](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)、 [トランザクションID](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)、 [訪問者ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)、 [フル処理](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)）。For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC).

作成したら、テンプレートをダウンロードし、テンプレートにデータを入力して、このデータをデータソースの FTP サイトにアップロードできます。データソースサーバーによって処理されると、インポートしたデータがAnalyticsレポートで使用できるようになります。

データソーステンプレートは .txt ファイルで、任意のテキストエディターで開くことができます。ただし、このテンプレートを編集するときは、Microsoft Excel などのスプレッドシートアプリケーションを使用した方が簡単です。テンプレートのコンテンツは、データソース有効化ウィザードでの選択内容によって異なります。

詳しくは、「[インポートファイルの参照](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD)」を参照してください。

1. Analytics へのログイン.
1. In the Suite header, select **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. **[!UICONTROL 「データソース作成]** 」タブで、テンプレートのカテゴリとタイプを選択します。
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   手順1.データソース有効化ウィザードで、テンプレートの作成オプションを選択します。

   | ウィザードのページ | フィールド | 説明 |
   |--- |--- |--- |
   | 1 | 名前 | Analyticsがデータソースマネージャーに表示するテンプレート名。 |
   | 1 | 電子メール | このデータソーステンプレートの使用に関連するすべての通知を受信する電子メールアドレス。 |
   | 1 | 関連する費用についてのチェックボックス | このチェックボックスを選択して、このデータソーステンプレートの使用に関連する費用の許容を示します。 |
   | 2 | 指標の選択 | このデータソースを使用してインポートする指標を選択します。手順3で選択したデータソースのカテゴリとタイプに基づいて、特定の指標が推奨されます。異なる指標を指定する場合、空のフィールドにこの指標名を入力し、チェックボックスをオンにしてこの指標を有効にします。 |
   | 3 | 指標をマッピング | "Analyticsイベント」を選択して、ウィザードページ2で選択した各インポート指標を受信します。このイベントは、新規の割り当てられていないイベントで、このイベントがデータソースから受け取る、インポートされる指標データに対応した名前が付けられている必要があります。格納先の変数が eVar、製品またはトラッキングコード変数で、アップロードされた値が既存の取り込まれた値に一致する場合、基本的にはアップロードされたイベントによって既存の値に指標が追加されます。例えば、「オフライン購入回数」指標を作成し、製品表示、チェックアウトおよび購入回数が既存の指標として定義されている製品データディメンションを含めることができます。 |
   | 4 | データディメンションの選択 | このデータソースからインポートされる指標を分類するデータディメンションを選択します。手順3で選択したデータソースタイプに基づいて、特定のデータディメンションが推奨されます。異なるデータディメンションを指定する場合、空のフィールドにこのディメンション名を入力し、チェックボックスをオンにしてこのデータディメンションを有効にします。 |
   | 5 | データディメンションのマッピング | ウィザードの 4 ページ目で選択した、インポートされるデータディメンションごとに、このディメンションを受け取る標準レポートまたは eVar を選択します。 |

1. テンプレートの作成後、データをデータソーステンプレートの適切な列にコピーし、そのデータ列に要求されるデータフォーマットに従っていることを確認します。

   手順1.データソースファイルを保存します。命名規則は任意です。アドビでは、すべてのデータソースファイルで一貫した命名規則を使用することをお勧めします。.txt や .tsv などの一般的なファイル拡張子を使用してください（拡張子なしのファイル名を使用しても問題ありません）。

