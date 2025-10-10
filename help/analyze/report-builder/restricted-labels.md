---
title: Report Builder の制限ラベルとは
description: Report Builder の制限ラベルについて説明します
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: aa2182f9-a140-4239-b2fb-f723e2767260
source-git-commit: c333a82848ed74a002a07f8c5e2857426a78425c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 49%

---

# Report Builder の制限ラベル

通常、Adobe Analyticsのデータガバナンス関連の設定は、Adobe Experience Platformから継承されます。 Adobe AnalyticsとAdobe Experience Platform Data Governance の統合により、Adobe Analyticsの機密データのラベル付けとプライバシーポリシーの実施が可能になります。

Experience Platformで使用されるデータセットに関して作成されたプライバシーラベルおよびポリシーは、Adobe Analytics レポートスイートワークフローで表示できます。 これらのラベルにより、ユーザーが機密性の高いフィールドから指標やディメンションを作成しようとしても、それができなかったり警告が表示されたりします。データセットについて詳しくは、[データセットの概要](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=ja)を参照してください。

また、データがAdobe Analyticsから（レポート、書き出し、API などを介して）書き出されると、警告またはラベルが追加されて、特定の方法で扱う必要のある機密情報がレポートに含まれていることをユーザーに知らせます。

この統合により、コンプライアンスを管理しやすくなります。組織のデータ管理人は、使用を制限するポリシーを設定できます。その結果、Adobe Analytics ユーザーは、データ管理人が定義したポリシーにデータが準拠していることを認識したうえで、より自信を持ってデータを使用できます。

詳しくは、[Adobe Analyticsとデータガバナンスを参照してください ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html?lang=ja)

## Report Builder の制限付きデータの表示

Adobe Analyticsでは、次の 2 つのAdobeで定義されるポリシーが表示され、レポート、ダウンロードおよび共有に影響します。

* Analytics の適用ポリシー
* ダウンロードの適用ポリシー

これらのポリシーの影響を受けるコンポーネントはグレー表示されます。 ポリシーが適用されているコンポーネントの上にマウスポインターを置くと、次の内容を示すメモが表示されます。**このデータの使用を禁止するポリシーがこのフィールドに適用されました。**&#x200B;詳しくは、[ラベルとポリシー](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html?lang=ja)を参照してください。

![ データの使用禁止を示すポリシーノート ](assets/rb-restricted-label.png)

## 制限付きデータを含むレポートの更新

ユーザーが後で制限されるデータ要素を含む Report Builder レポートを作成した場合、レポートを更新すると、エラーメッセージが表示されます。

![ データ要素が後で制限された後に表示されるエラーメッセージ。](assets/error-restricted-data.png)
