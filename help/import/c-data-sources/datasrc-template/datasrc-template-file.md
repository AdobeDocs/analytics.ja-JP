---
description: データソーステンプレートに関する情報です。データソーステンプレートは、特定の外部データのセットをデータソースに送信するのに適したデータの枠組みを提供します。
subtopic: Data sources
title: データソーステンプレートの概要
topic: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 100%

---


# データソーステンプレートの概要

データソーステンプレートに関する情報です。データソーステンプレートは、特定の外部データのセットをデータソースに送信するのに適したデータの枠組みを提供します。

このウィザードで作成されるテンプレートファイルは、慣れないお客様がインポート機能を簡単に使用できるように設計されています。使用できる列はテンプレートで定義されているものに限られません。含める指標やディメンションが選択した処理タイプでサポートされている限り、必要に応じて列を追加することができます。

各タイプでサポートされる指標やディメンションは、

* [Web ログ](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [トラフィック](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)（現在はサポートされていません）
* [コンバージョン](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [トランザクション ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [訪問者 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [フル処理](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

例えば、訪問者 ID データタイプの場合は、[訪問者 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md) にリストされる指標やディメンションに列を追加できます。

作成したら、テンプレートをダウンロードし、テンプレートにデータを入力して、このデータをデータソースの FTP サイトにアップロードできます。データソースサーバーで処理されると、インポートされたデータをマーケティングレポートで使用できるようになります。

データソーステンプレートは [!DNL .txt] ファイルで、任意のテキストエディターで開くことができます。ただし、このテンプレートを編集するときは、Microsoft Excel などのスプレッドシートアプリケーションを使用した方が簡単です。テンプレートの内容は、[!UICONTROL データソース有効化ウィザード]での選択内容によって異なります。

詳しくは、「[インポートファイルの参照](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)を参照してください。
