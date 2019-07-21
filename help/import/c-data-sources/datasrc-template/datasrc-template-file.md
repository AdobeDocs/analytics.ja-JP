---
description: データソーステンプレートに関する情報です。データソーステンプレートは、特定の外部データのセットをデータソースに送信するのに適したデータの枠組みを提供します。
seo-description: データソーステンプレートに関する情報です。データソーステンプレートは、特定の外部データのセットをデータソースに送信するのに適したデータの枠組みを提供します。
seo-title: データソーステンプレートの概要
solution: Analytics
subtopic: データソース
title: データソーステンプレートの概要
topic: 開発者と導入
uuid: e768bcff- a996-44c7- a7f2-9a2c651ecad9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# データソーステンプレートの概要

データソーステンプレートに関する情報です。データソーステンプレートは、特定の外部データのセットをデータソースに送信するのに適したデータの枠組みを提供します。

このウィザードで作成されるテンプレートファイルは、慣れないお客様がインポート機能を簡単に使用できるように設計されています。使用できる列はテンプレートで定義されているものに限られません。含める指標やディメンションが選択した処理タイプでサポートされている限り、必要に応じて列を追加することができます。

各タイプでサポートされる指標やディメンションは、

* [Web ログ](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)
* [トラフィック](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC)（現在はサポートされていません）
* [コンバージョン](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)
* [トランザクション ID](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)
* [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)
* [フル処理](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5).

作成したら、テンプレートをダウンロードし、テンプレートにデータを入力して、このデータをデータソースの FTP サイトにアップロードできます。データソースサーバーで処理されると、インポートされたデータをマーケティングレポートで使用できるようになります。

The Data Source template is a [!DNL .txt] file that you can open with any text editor. ただし、このテンプレートを編集するときは、Microsoft Excel などのスプレッドシートアプリケーションを使用した方が簡単です。テンプレートの内容は、[!UICONTROL データソース有効化ウィザード]での選択内容によって異なります。

詳しくは、「[インポートファイルの参照](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD)」を参照してください。
