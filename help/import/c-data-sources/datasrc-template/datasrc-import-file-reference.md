---
description: データソースの .txt テンプレートに関する情報です。
subtopic: Data sources
title: インポートファイルの参照
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 7966b156-04bf-4d39-a720-ab47a665d1e2
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---

# インポートファイルの参照

データソースの .txt テンプレートに関する情報です。

インポートテンプレートを生成するには、データソースウィザードを使用します。データソースのインポートファイルには、次のようなデータが含まれます。

* シャープ記号（#）は、その行がコメントであることを示します。
* 必要に応じて、ファイルにコメントを追加できます。
* テンプレートファイルのタイトルを示すコメント。
* [!UICONTROL データソース有効化ウィザード]で指定された外部の指標およびデータディメンションの名前を示すコメント。

列見出しは、データソースファイルの各列のデータを識別するのに使用されます。列見出しには次の 3 つのタイプがあります。

**日付**：（必須）ファイル内の各データ行のタイムスタンプ（`m/d/yyyy` 形式）。

**変数**：データソースのデータディメンションにマッピングされているレポート変数の名前。

**イベント**：データソースの指標にマッピングされているイベントの名前。

データソーステンプレートを使用して、アップロードするデータを含むデータソースファイルを作成します。データソースファイルを作成する場合、以下の点に注意してください。

* データソースファイルの各行にデータレコードが 1 つずつ含まれます。各レコードは一連のタブ区切りのフィールドで構成されます。データソーステンプレートの列見出しによって、これらのフィールドの順序が決まります。次に例を示します。

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* 複数のデータファイルをアップロードする場合、データソースでこれらのファイルがアルファベット順に読み込まれます。ファイルを時間順に処理する必要がある場合、これらのファイルのアルファベット順が時間順に一致するようにファイル名を付ける必要があります。次に例を示します。

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* データソースファイルの処理速度を向上させるために、1 つの日付に関するイベント（指標）データを 1 つの行にまとめることをお勧めします。

   例えば、データソースファイルで広告インプレッションデータがイベント 6 にマッピングされている場合、特定の日に発生した各広告インプレッションについて個別のデータ行エントリを作成するのではなく、広告インプレッションの合計数を日別で表示する 1 つのデータ行を作成します。
* レポートスイートの作成日より前の日からのデータをアップロードする必要がある場合は、アカウントマネージャーに連絡して、レポートを実行可能な最も古い日付を変更してください。

**FIN ファイル**

データソースファイルの入力が完了すると、そのファイルを Analytics に FTP で送信できます。ただし、データを処理するためにはファイルがもう 1 つ必要です。データファイルと同じ名前で、拡張子が [!DNL .fin] の空のテキストファイルをアップロードする必要があります。

例えば、[!DNL myproductdata.txt] という（タブ区切りの）データファイルをアップロードする場合、[!DNL myproductdata.fin] という空のテキストファイルもアップロードする必要があります。この [!DNL .fin] ファイルがないと、データは処理されません。
