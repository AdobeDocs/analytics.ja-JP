---
description: 現在、Adobe Report Builder には、Analytics 管理ツールの権限設定に似た権限設定があります。
title: ディメンションおよび指標のユーザーアクセス権限
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
TQID: https://experienceleague.adobe.com/p-nsvA1hqNBbwXesj5cumraamq2nEk1zVHgbby-XwEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 40%

---

# ディメンションおよび指標のユーザーアクセス権限

{{legacy-arb}}

Adobe Report Builderでは、Analytics管理ツールと同様の権限設定が行われます。

管理者以外のユーザーとして、アクセス権のないディメンションと指標を指すリクエストを含むワークブックを以前に作成したことがある場合があります。 これらの権限が適用されます。

例えば、アクセス権のないディメンションまたは指標を含むリクエストを更新すると、制限付き権限エラーが表示されます。 エラーメッセージは、管理者権限が原因で、ユーザーアカウントでリクエストを利用できないことを示しています。

制限付き権限エラーメッセージを表示する![&#x200B; スクリーンショット。](assets/arb_restrc_perm.png)

管理する&#x200B;**各** Report Builder ワークブックの手順に従います。

1. ワークブックを開きます。
1. すべてのリクエストを更新します。
1. ユーザーアクセス権限エラーが表示された場合は、**[!UICONTROL CSV ファイルを開く]**&#x200B;をクリックして、制限付き権限エラーのリストにアクセスします。
1. ファイル「AllRestrictedPermissionErrors.xlsx」を作成し、制限付き権限エラーの一覧を CSV ファイルからコピーして、このファイルに貼り付けます。
1. Report Builder ワークブックを閉じます。

すべてのワークブックを処理したら、「AllRestrictedPermissionErrors.xlsx」に制限付き権限エラーのすべての一覧が完成します。 この一覧を Adobe Analytics のユーザーアクセス管理者に送信して、該当する指標およびディメンションへのアクセス権を付与するように依頼します。
