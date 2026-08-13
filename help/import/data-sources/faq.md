---
title: データソース FAQ
description: データソースに関するよくある質問。
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
TQID: 'https://experienceleague.adobe.com/RS75oqFMxi3GsiNkcqTUKAVEvlHVo9bLiR2Nt-cVU74'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: f46a60da-b0b2-4ca3-bd91-271173f4123d
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 430
ht-degree: 3%

---

# データソース FAQ

データソースに関するよくある質問。

+++データソースの使用コスト？
データソースには料金は発生せず、サーバーコールの使用にカウントされません。 [完全な処理データソース ](full-processing-eol.md)は、退職前にサーバーコールにカウントされました。
+++

+++データソースは、eVarのアトリビューションと有効期限にどのような影響を与えますか？
データソースにはアトリビューションや有効期限はありません。
+++

+++データソースは、ページビュー数、訪問数、実訪問者数などの指標にどのような影響を与えますか？
データソースを通じてアップロードされたデータは、[ ページビュー](/help/components/metrics/page-views.md)、[訪問](/help/components/metrics/visits.md)、[ ユニーク訪問者](/help/components/metrics/unique-visitors.md)には影響しません。 影響を与えるデフォルトの指標は[発生回数](/help/components/metrics/occurrences.md)のみです。
+++

+++データソースを通じてアップロードされたデータは、処理ルールなどの追加の処理を通じて処理されますか？
いいえ。 データソースを通じてアップロードされたデータ：

* [処理ルール ](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)を通過しません
* [ マーケティングチャネル処理ルール ](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)を通過しません
* [VISTA ルール ](/help/technotes/vista.md)を実行しません
+++

+++データソースを使用してインポートされたデータを削除できますか？
はい。 このデータは、[ データ修復API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)を使用して削除できます。 Adobeでは、データを削除する必要性を減らすために、データソースデータをテストレポートスイートにアップロードしてから、実稼動レポートスイートにアップロードすることを強くお勧めします。
+++

+++一度にどれだけのデータを読み込むことができますか？
サイズが50 MBを超え、合計が50 MB未満になるまで処理が再開されない場合、処理は一時停止します。 FTP サイト上のすべてのファイルの合計サイズが50 MB未満であることを確認します。
+++

+++データソースを通じてレポートに負の値を渡すとどうなりますか？
それに応じて値が減少します。 一部の組織では、データを修正するためにネガティブデータソースの値を使用しています。 負のデータソース値は、望ましくない可能性がある方法や予期しない方法でレポートに影響を与える可能性があります。 Adobeでは、最後の手段としてのみ、データソースで負の値を使用することをお勧めします。
+++

+++ファイル拡張子は大文字と小文字を区別しますか？
はい。 拡張子が`.TXT`または`.FIN`のファイルは処理されません。 ファイル拡張子がすべて小文字であることを確認します。
+++

+++データソースファイルに追加できる列の数は？
すべての列が有効な場合は、必要な数の列をデータソースファイルに含めることができます。 有効な変数名/列名のリストについては、[ ファイル形式](file-format.md)を参照してください。
+++

+++Adobeが提供するFTPの場所を使用せずにデータソースを使用できますか？
[ データソース API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)を使用すると、API呼び出しをAdobeに直接送信できます。 これらのAPI呼び出しには`UploadData` メソッドが含まれており、JSON オブジェクトペイロードでデータを送信できます。
+++
