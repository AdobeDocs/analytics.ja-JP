---
title: ユニーク訪問者
description: ユニーク訪問者 ID の数。
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: e242276f931e9939081b948a9d9ef8a087e16461
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 95%

---

# ユニーク訪問者

「ユニーク訪問者」[指標](overview.md)は、ディメンション項目の訪問者 ID の数を示します。トラフィックを決定する際に使用される最も一般的な指標の 1 つで、ディメンション項目の人気度の概要を示します。例えば、ある訪問者が 1 か月間毎日サイトを訪問しても、1 人のユニーク訪問者としてカウントされることがあります。

[デバイス間の分析](../cda/overview.md)を使用する場合、この指標は、[一意のデバイス](unique-devices.md)指標に置き換えられます。

## 日別、週別、月別、四半期別、年別のユニーク訪問者

Analysis Workspace は、レポートの精度に基づいてユニーク訪問者を処理します。例えば、[日](../dimensions/day.md)ディメンションを使用すると、各ディメンション項目の日別ユニーク訪問者が表示されます。ただし、レポートの合計に対しては、フリーフォームテーブルの日付範囲で重複したユニーク訪問者が排除されます。

## この指標の計算方法

この指標は、特定のディメンション項目に対するユニーク訪問者 ID の数をカウントします。ユニーク訪問者を識別する方法はいくつかあるので、複数の高度なメカニズムを使用してユニーク訪問者を識別します。次の表に、訪問者の識別方法と優先度を示します。ヒットによっては、複数の訪問者識別方法を持つ場合があります。 この場合は、優先度の高い方法を使用します。

| 使用順序 | クエリパラメーター（収集方法） | 以下の場合に表示される |
| --- | --- | --- |
| 1 | `vid` | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) 変数が設定されます。 |
| 2 | `aid` | 訪問者に既存の [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja) Cookie があります。訪問者 ID サービスを実装しない、または実装する前に設定します。 |
| 3 | `mid` | 訪問者に既存の [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja) Cookie があります。[Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja) を使用した実装に設定します。 Adobeでは、可能な限り、すべての実装に ID サービスを使用することをお勧めします。 |
| 4 | `fid` | 訪問者に既存の [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=ja) Cookie がある、または何らかの理由で `aid` と `mid` を設定できなかった場合。 |
| 5 | IP アドレス、ユーザーエージェント、ゲートウェイ IP アドレス | 最後の手段は、訪問者のブラウザーが cookie を受け入れない場合にユニーク訪問者を識別することです。 |

>[!NOTE]
>
>各 Analytics 訪問者 ID は、アドビのサーバー上のプロファイルに関連付けられます。訪問者プロファイルは、少なくとも 13 ヶ月操作が実行されなかった場合、訪問者 ID cookie の有効期限にかかわらず削除されます。

## ユニーク訪問者数に影響する動作

ユニーク訪問者識別子は、通常、ブラウザーの Cookie に保存されます。新しいユニーク訪問者は、次のいずれかの操作を実行するとカウントされます。

* キャッシュをクリアする（どの時点でも）
* 同じコンピューターで別のブラウザーを開く -ブラウザーごとにユニーク訪問者が 1 回カウントされます。
* 同じ訪問者が異なるデバイスでサイトを閲覧した -デバイスごとにユニーク訪問者が 1 回カウントされます。[クロスデバイス分析](../cda/overview.md)を使用すると、[人](people.md)指標を使用して訪問者を組み合わせることができます。
* プライベートブラウジングセッション（Chrome の「シークレットウィンドウ」など）を開く

Cookie 識別子が保持されている限り、新しいユニーク訪問者はカウント&#x200B;*されません*。

* 長期間ブラウザーを閉じる
* ブラウザーを最新バージョンにアップグレードする
