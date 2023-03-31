---
description: 内部 URL フィルターは、サイト内部のリファラーを識別します。トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。
title: 内部 URL フィルター
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 2beb4cd38fc8b48e2b34468a4570f7168aeacb78
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 30%

---


# 内部 URL フィルター

内部 URL フィルターを使用すると、サイト内部と見なすリファラーを特定できます。 トラフィックソースレポートにデータを入力したり、内部トラフィックにフィルターをかけるのに役立ちます。

リファラー（参照元ページ）は、通常訪問者がサイトを訪問する前に表示したページです。データの歪曲を避けるために、自社の内部リファラーをフィルターして除外できます。レポートでは、[転送者](/help/components/dimensions/referrer.md)ディメンション、[参照ドメインディメンション](/help/components/dimensions/referring-domain.md)、および他のトラフィックソースディメンションからフィルターされた転送者を除外します。

## 既存の内部 URL フィルターを表示

>[!NOTE]
>
>一部のレポートスイートには、ピリオド (.) の内部 URL フィルターがあります デフォルトで設定されます。 このフィルターが存在する場合、すべてのトラフィックは内部トラフィックとして分類されます。 リファラーレポートは、ピリオド (.) が付くまで機能しません。 フィルターが削除されました。

レポートスイートに対して設定されている内部 URL フィルターを確認するには： <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")-->

1. 選択 **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** 」をクリックして Report Suite Manager にアクセスします。

1. どの内部 URL フィルターが設定されているかを確認するレポートスイートを選択し、「 **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL 内部 URL フィルター]**.

   既存のすべてのフィルターは、 [!UICONTROL **現在のフィルター**] 」セクションに入力します。

## レポートスイートに内部 URL フィルターを追加する

1. 選択 **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** 」をクリックして Report Suite Manager にアクセスします。

1. 内部 URL フィルターを追加するレポートスイートを選択し、「 **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL 内部 URL フィルター]**.

1. 「フィルターを追加」セクションで、指定したフィールドにフィルターを適用するページの URL を入力し、「 」を選択します。 [!UICONTROL **追加**].

   追加した URL が [!UICONTROL **現在のフィルター**] 」セクションに入力します。
