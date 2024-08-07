---
title: データソース FAQ
description: データソースに関するよくある質問です。
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: f7d07525c97f4aa145dc46198f883a37cde80158
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---

# データソース FAQ

データソースに関するよくある質問です。

+++データソースを使用するためのコストはどれくらいですか？
データソースには料金は発生せず、サーバーコールの使用状況にもカウントされません。 [ フル処理データソース ](full-processing-eol.md) 廃止前のサーバーコールに対してカウントされます。
+++

+++データソースは、eVar のアトリビューションと有効期限にどのような影響を与えますか？
データソースとオンラインヒットの間で transactionID が一致した場合、関連するeVar値は、オンラインヒットで設定されたかのように、同じアトリビューションおよび有効期限を想定します。

データソースからアップロードされた他のすべてのデータには、アトリビューションや有効期限はありません。
+++

+++データソースは、ページビュー、訪問回数、ユニーク訪問者などのデフォルトの指標にどのような影響を与えますか？
データソースを通じてアップロードされたデータは、[ ページビュー数 ](/help/components/metrics/page-views.md)、[ 訪問回数 ](/help/components/metrics/visits.md)、または [ ユニーク訪問者 ](/help/components/metrics/unique-visitors.md) には影響しません。 影響を受けるデフォルトの指標は [ 回数 ](/help/components/metrics/occurrences.md) のみです。
+++

+++データソースを使用してインポートされたデータを削除することはできますか？

はい。このデータは、[Data Repair API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/) を使用して削除できます。 また、Adobeでは、データソースデータを実稼動レポートスイートにアップロードする前に、テストレポートスイートにアップロードすることを強くお勧めします。
+++

+++一度にどのくらいのデータを読み込むことができますか？

データサイズが 50 MB を超えると処理が一時停止し、合計 50 MB 未満になるまで再開しません。FTP サイト上のすべてのファイルの合計サイズが 50 MB 未満であることを確認してください。
+++

+++データソースからレポートに負の値を渡すとどうなりますか？

それに応じて値が減少します。 組織によっては、データを修正するために負のデータソース値を使用します。 データソース値が負の場合、望ましくない場合や予期しない方法でレポートに影響を与える可能性があります。 Adobeでは、最後の手段としてのみ負のデータソースを使用することをお勧めします。
+++

+++ファイル拡張子では大文字と小文字が区別されますか？
はい。拡張子が `.TXT` または `.FIN` のファイルは処理されません。 ファイル拡張子がすべて小文字であることを確認します。
+++

+++データファイルに追加できる列はいくつですか？
データ ソース ファイルに含める列の数は、すべての列が有効な場合に任意に指定できます。 有効な変数名または列名のリストについては、[ ファイル形式 ](file-format.md) を参照してください。
+++

+++Adobeが提供する FTP の場所を使用せずにデータソースを使用できますか？
[Data sources API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/) を使用すると、API 呼び出しをAdobeに直接送信できます。 これらの API 呼び出しには、JSON オブジェクトペイロードでデータを送信できる `UploadData` メソッドが含まれています。
+++
