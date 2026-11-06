---
description: サーバーサイド転送の特徴、機能、問題に関するよくある質問です。
title: サーバー側転送の FAQ
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: 'https://experienceleague.adobe.com/av541DJd5Ga5QaK2856YBHWW1M-JjkbzRs8JXxYma6c'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 0ba418a49e6a226540e0791f0138027566022d6f
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 46%
---
# サーバー側転送の FAQ

サーバーサイド転送の特徴、機能、問題に関するよくある質問です。

## トラッキングサーバー {#section_28E5BECC2034484AB9726E513F2CCFB7}

| 質問 | 回答 |
|--- |--- |
| Q：現在従来のトラッキングサーバーベースのサーバーサイド転送を使用している場合はどうなりますか。 | 従来のトラッキングサーバーベースのサーバーサイド転送方式では、引き続きAnalyticsからAudience Managerにデータが転送されますが、Audience Manager セグメントをAnalyticsに送信する場合は、新しいレポートスイートベースのサーバーサイド転送が必要になります。 さらに、トラッキングサーバー設定に加えてサーバーサイド転送のレポートスイートを有効にしても問題はありません。新しいレポートスイートのサーバーサイド転送設定は、競合が発生するたびに使用されます。 |
| Q：従来のトラッキングサーバーベースのサーバーサイド転送を、新しいレポートスイートベースのサーバーサイド転送に移行すべきでしょうか？ | 今後も引き続きトラッキングサーバーベースのサーバーサイド転送をサポートしますが、Audience ManagerからAnalyticsへの統合（セグメント共有）を利用する場合は、該当するすべてのレポートスイートで新しいレポートスイートベースのサーバーサイド転送を有効にする必要があります。 ただし、従来のトラッキングサーバーベースのサーバーサイド転送を無効にする緊急の理由はありません。 |

## Tagging and Reporting {#section_71391BA901AC47B9A2286281644FF281}

| 質問 | 回答 |
|--- |--- |
| Q：サイトでマルチスイートタグ付けを利用している場合はどうなりますか？ サーバーサイド転送によって Audience Manager へのサーバーコールが 2 倍になりますか？ | いいえ。Analytics から Audience Manager に転送されるヒットは、ヒット内のレポートスイートの数に関係なく、1 回だけ Audience Manager に送信されます。 ヒット内の各レポートスイートに対して Audience Manager に対応するデータソースがある場合、それぞれがその単一のヒットから適切にデータが取り込まれます。  ただし、現在クライアントサイドのデータ収集（DIL）を使用していて、Audience Management モジュールをインストールせずにサーバーサイド転送を有効にした場合は、Analytics のヒット内のレポートスイートの数に関係なく、Audience Manager へのサーバーコールが 2 倍になることに注意してください。 |
| 質問：複数のスイートタグ付きレポートスイートがあり、個別のAdobe組織にマッピングされている場合はどうなりますか？ | 単一のAnalytics ヒットから別々の組織に属する2つのレポートスイートにデータを送信しないでください。ただし、これが発生した場合は、ページの訪問者ID サービス設定に一致する組織にのみヒットを転送します。 |
| Q: マルチスイートタグ付けがあり、レポートスイートの1つだけが組織にマッピングされ、他のレポートスイートがマッピングされていない場合はどうなりますか？ | マッピングされたレポートスイート上の組織の対応するデータ収集サーバーにヒットを転送しますが、マッピングされていないレポートスイートにはAudience Managerに関連付けられたデータソースがないため、マッピングされていないレポートスイートのデータはAudience Managerに記録されません。 |
| 質問：複数の組織にマッピングされたレポートスイートがある場合はどうなりますか？ | Analytics ではこのレポートスイートはマッピングされていないと見なされるため、このレポートスイートに対してサーバーサイド転送を有効にすることはできません。 このマッピングの問題を解決するには、カスタマーケアにお問い合わせください。 |
| Q：レポートスイートベースのサーバーサイド転送手法は、トラッキングサーバーベースのサーバーサイド転送より低速ですか？ | いいえ。応答時間は同じです。 |
| 質問：2つの組織（またはAdobe Audience Manager インスタンス）があり、両方の組織間でデータを共有する場合はどうなりますか？ 単一のAnalytics ヒットを複数の組織にサーバーサイドで転送できますか？ | いいえ。 ある組織で収集したデータを別の組織に共有する必要がある場合は、Audience Marketplaceを使用して、あるAudience Manager インスタンスから別のインスタンスに該当するオーディエンスを送信することをお勧めします。 |
| Q：サーバーサイド転送によって Audience Manager または Analytics で追加の請求が発生しますか？ | Analytics では、追加の請求は発生しません。 Audience Manager では、転送されたヒットは他のヒットと同じように扱われ、請求されます。  これが、DIL とサーバーサイド転送を同時に有効にしないことが重要である理由です。同時に有効にすると、データの重複が発生するだけでなく、二重課金が発生する可能性があります。 |

>[!MORELIKETHIS]
>
>* [サーバー側転送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
