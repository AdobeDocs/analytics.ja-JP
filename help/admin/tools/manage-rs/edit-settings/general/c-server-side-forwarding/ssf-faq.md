---
description: サーバー側転送の特徴、機能、問題に関するよくある質問です。
title: サーバー側転送の FAQ
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: 'https://experienceleague.adobe.com/av541DJd5Ga5QaK2856YBHWW1M-JjkbzRs8JXxYma6c'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 707
ht-degree: 45%

---

# サーバー側転送の FAQ

サーバー側転送の特徴、機能、問題に関するよくある質問です。

## トラッキングサーバー {#section_28E5BECC2034484AB9726E513F2CCFB7}

| 質問 | 回答 |
|--- |--- |
| Q：現在従来のトラッキングサーバーベースのサーバー側転送を使用している場合はどうなりますか？ | 従来のトラッキングサーバーベースのサーバーサイド転送方式では、引き続きAnalyticsからAudience Managerにデータが転送されますが、Audience Manager セグメントをAnalyticsに送信する場合は、新しいレポートスイートベースのサーバーサイド転送が必要になります。 さらに、トラッキングサーバー設定に加えてサーバーサイド転送のレポートスイートを有効にしても問題はありません。新しいレポートスイートのサーバーサイド転送設定は、競合が発生するたびに使用されます。 |
| Q：従来のトラッキングサーバーベースのサーバー側転送を新しいレポートスイートベースのサーバー側転送に移行する必要がありますか？ | 今後も引き続きトラッキングサーバーベースのサーバーサイド転送をサポートしますが、Audience ManagerからAnalyticsへの統合（セグメント共有）を利用する場合は、該当するすべてのレポートスイートで新しいレポートスイートベースのサーバーサイド転送を有効にする必要があります。 ただし、従来のトラッキングサーバーベースのサーバーサイド転送を無効にする緊急の理由はありません。 |

## Tagging and Reporting {#section_71391BA901AC47B9A2286281644FF281}

| 質問 | 回答 |
|--- |--- |
| Q：サイトでマルチスイートタギングを利用している場合はどうなりますか？ サーバー側転送によって Audience Manager へのサーバーコールが 2 倍になりますか？ | いいえ。Analytics から Audience Manager に転送されるヒットは、ヒット内のレポートスイートの数に関係なく、1 回だけ Audience Manager に送信されます。 ヒット内のレポートスイートのそれぞれに対して Audience Manager に対応するデータソースがある場合、それぞれが単一のヒットから適切に設定されます。  ただし、現在クライアント側データ収集（DIL）を使用していて、Audience Management モジュールをインストールせずにサーバー側転送を有効にした場合は、Analytics ヒット内のレポートスイートの数に関係なく Audience Manager へのサーバーコールが 2 倍になることに注意してください。 |
| 質問：個別のCX Enterprise組織にマッピングされたマルチスイートタグ付きレポートスイートがある場合はどうなりますか？ | 1つのAnalytics ヒットから、別々のCX Enterprise組織に属する2つのレポートスイートにデータを送信しないでください。ただし、これが発生した場合は、ページのID サービス設定に一致するCX Enterprise組織にのみヒットを転送します。 |
| Q: マルチスイートタグ付けがあり、レポートスイートの1つだけがCX Enterprise組織にマッピングされ、もう1つがそうでない場合はどうなりますか？ | マッピングされたレポートスイート上のCX Enterprise Orgに対応するデータ収集サーバーにヒットを転送しますが、マッピングされていないレポートスイートにはAudience Managerに関連するデータソースがないため、マッピングされていないレポートスイートのデータはAudience Managerに記録されません。 |
| 質問：複数のCX Enterprise組織にマッピングされているレポートスイートがある場合はどうなりますか？ | Analytics によってこのレポートスイートはマッピングされていないと見なされるので、このレポートスイートに対してサーバー側転送を有効にできません。 このマッピングの問題を解決するには、カスタマーケアにお問い合わせください。 |
| Q：レポートスイートベースのサーバー側転送手法はトラッキングサーバーベースのサーバー側転送より低速ですか？ | いいえ。応答時間は同じです。 |
| 質問：2つのCX Enterprise組織（またはAdobe Audience Manager インスタンス）があり、両方のCX Enterprise組織間でデータを共有する場合はどうなりますか？ 1つのAnalytics ヒットを複数のCX Enterprise組織にサーバーサイドで転送できますか？ | いいえ。 あるCX Enterprise組織で収集したデータを別のCX Enterprise組織に共有する必要がある場合は、Audience Marketplaceを使用して、あるAudience Manager インスタンスから別のインスタンスに該当するオーディエンスを送信することをお勧めします。 |
| Q：サーバー側転送によって Audience Manager または Analytics で追加の請求が発生しますか？ | Analytics では、追加の請求は発生しません。 Audience Manager では、転送されたヒットは他のヒットと同じように扱われ、請求されます。  これが、DIL とサーバー側転送を同時に有効にしないことが重要である理由です。この場合、データの重複が発生するだけでなく、2 重に課金されることになります。 |

>[!MORELIKETHIS]
>
>* [サーバー側転送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
