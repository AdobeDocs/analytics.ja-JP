---
description: インポートテンプレートファイルの目的は、インポートを開始できるようにすることです。
subtopic: Data sources
title: インポートファイルテンプレートの作成
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# インポートファイルテンプレートの作成

インポートテンプレートファイルの目的は、インポートを開始できるようにすることです。

使用できる列はテンプレートで定義されているものに限られません。含める指標やディメンションが選択した処理タイプでサポートされている限り、必要に応じて列を追加することができます。各タイプでサポートされる指標やディメンションは、 Web Log [, Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [Conversion](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Transaction TransactionTransaction](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)Visitor Id, Visitor Id, Full Processing Full Processing The The Log. For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

作成したら、テンプレートをダウンロードし、テンプレートにデータを入力して、このデータをデータソースの FTP サイトにアップロードできます。データソースサーバーで処理されると、インポートされたデータをAnalyticsレポートで使用できるようになります。

データソーステンプレートは .txt ファイルで、任意のテキストエディターで開くことができます。ただし、このテンプレートを編集するときは、Microsoft Excel などのスプレッドシートアプリケーションを使用した方が簡単です。テンプレートのコンテンツは、データソース有効化ウィザードでの選択内容によって異なります。

詳しくは、「[インポートファイルの参照](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)」を参照してください。

1. Analytics へのログイン.
1. In the Suite header, select **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   手順の結果 1データソース有効化ウィザードで、テンプレートの作成オプションを選択します。

   | ウィザードのページ | フィールド | 説明 |
   |--- |--- |--- |
   | 1 | 名前 | Analyticsがデータソースマネージャーに表示するテンプレート名です。 |
   | 1 | 電子メール | このデータソーステンプレートの使用に関連するすべての通知を受信する電子メールアドレス。 |
   | 1 | 関連する費用についてのチェックボックス | このデータソーステンプレートの使用に関連する料金に対する同意を示すチェックボックスを選択します。 |
   | 2 | 指標の選択 | このデータソースを使用してインポートする指標を選択します。手順3で選択したデータソースのカテゴリとタイプに基づいて、Analyticsが推奨する指標を示します。  異なる指標を指定する場合、空のフィールドにこの指標名を入力し、チェックボックスをオンにしてこの指標を有効にします。 |
   | 3 | 指標をマッピング | ウィザードの2ページ目で選択した、インポートされた各指標を受け取るAnalyticsイベントを選択します。  このイベントは、新規の割り当てられていないイベントで、このイベントがデータソースから受け取る、インポートされる指標データに対応した名前が付けられている必要があります。格納先の変数が eVar、製品またはトラッキングコード変数で、アップロードされた値が既存の取り込まれた値に一致する場合、基本的にはアップロードされたイベントによって既存の値に指標が追加されます。例えば、既存の指標として既に製品表示、チェックアウトおよび注文がある製品データディメンションを持つ「オフライン注文」指標を作成できます。 |
   | 4 | データディメンションの選択 | このデータソースからインポートされる指標を分類するデータディメンションを選択します。手順3で選択したデータソースタイプに基づいて、Analyticsでは特定のデータディメンションを推奨しています。  異なるデータディメンションを指定する場合、空のフィールドにこのディメンション名を入力し、チェックボックスをオンにしてこのデータディメンションを有効にします。 |
   | 5 | データディメンションのマッピング | ウィザードの 4 ページ目で選択した、インポートされるデータディメンションごとに、このディメンションを受け取る標準レポートまたは eVar を選択します。 |

1. テンプレートの作成後、データをデータソーステンプレートの適切な列にコピーし、そのデータ列に要求されるデータフォーマットに従っていることを確認します。

   手順の結果 1データソースファイルを保存します。命名規則は任意です。アドビでは、すべてのデータソースファイルで一貫した命名規則を使用することをお勧めします。.txtや.tsvなどの一般的なファイル拡張子を使用します（または拡張子を使用しない）。

