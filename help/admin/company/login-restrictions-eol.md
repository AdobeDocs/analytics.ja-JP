---
title: IPログイン制限の [!UICONTROL 使用終了]
description: 提供終了のタイミングと、 [!UICONTROL Enforce IP login restrictionsに関する影響について説明します。]
translation-type: tm+mt
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# IPログイン制限の [!UICONTROL 使用終了]

Adobe Analyticsの **[「IPログイン制限の強制](/help/admin/company/security-manager.md)** 」機能を使用すると、（セキュリティで保護されていると見なされる）特定のIPアドレスをホワイトリストに登録して、Adobe Analytics環境への正常なログインとアクセスを許可できます。 多くの場合、この機能は、ユーザがログインできる唯一のセキュアIPアドレスとして会社のIPアドレスを設定するために使用されます。 したがって、Adobe Analyticsを使用するには、ユーザーが会社のオフィスにいるか、VPN経由でネットワークにログインする必要があります。

この機能は2020年10月に提供終了となる予定です。

## この機能の提供終了の理由を教えてください。

この機能は、Experience cloudログイン移行またはExperience cloudログインによって、状況によって機能しなくなる場合があります。 顧客属性またはオーディエンスライブラリを使用する顧客 **[!UICONTROL に対して]** 、分類する **[!UICONTROL ことが知られています]**。

また、複数のExperience cloudソリューションを所有している場合は、他のソリューションの1つを使用してExperience cloudにログインすることで、この要件を回避できます。この機能は、Analytics自体の外部では存在しないか、サポートされていません。 また、IPスプーフィングを使用してこの問題を回避することもできます。

最後に、シングルサインオンとFederated IDを使用した、機能的で優れた代替ソリューションが提供されます。 この機能により、ユーザーのログインエクスペリエンスをより詳細に制御し、セキュリティを確保できます。 詳しくは、以下を参照してください。

## この機能を削除すると、どのように影響を受けますか。

「IPログイン制限の強制 **** 」が設定されているお客様の場合、この機能は2020年10月に削除されます。 現時点では、IPログイン制限は適用されなくなります。 それでもIPアドレスでログインを制限する必要がある場合は、シングルサインオンとFederated IDの推奨ソリューション（詳細情報とリソースは以下を参照）を確認し、実装する必要があります。

さらに、 **[!UICONTROL IPログイン制限の強制]** (以下に示すように **[!UICONTROLA)設定は、Analytics UIの管理者/カンパニー設定/セキュリティマネージャー]** (Demin)から削除されます。

![](assets/sec-manager2.png)

## 他の選択肢は？

上述のとおり、このAnalytics機能は提供終了となります。 SSOおよびFederated IDの実装に時間を割くため、EOLの日付を2020年10月に延期しました。

SSO IDとFederated IDの両方が、現在導入されているIPログイン制限機能に対する優れたソリューションであり、より詳細な制御、セキュリティ、機能を提供します。 SSO/Federated IDの設定方法について詳しくは、次のヘルプドキュメントを参照してください。 アドビでは、お客様のIT部門と協力して、導入を行うことをお勧めします。

* [シングルサインオンとExperience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [管理コンソール — ID設定ドキュメント](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [管理コンソール — ID設定チュートリアル（ビデオ）](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Federated IDの設定チュートリアル（ビデオ）（英語）](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [シングルサインオン — よくある質問](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [アドビがサポートするIDタイプ](https://helpx.adobe.com/enterprise/using/identity.html)

IPログイン制限のサポートを引き続き表明し、Experience cloudによる提供をリクエストする場合は、フォーラムページでこの機能に対して投票を行うこと [ができます](https://forums.adobe.com/ideas/11648)。