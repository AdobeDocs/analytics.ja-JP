---
description: アドビの FTP サーバーのアップグレードでは、特定のサーバー設定に依存した自動スクリプト（多くの場合、データを定期的にダウンロードまたはアップロードするために使用されます）に影響を与える新しい設定が導入されることがあります。
keywords: ftp;sftp
title: Adobe FTPおよびSFTP サーバーのアップグレード
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
TQID: 'https://experienceleague.adobe.com/RJHgVwgnmCLRuNTyjKx-D6SlOovFYS0T5-7topZkcVY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 25%

---

# Adobe FTPおよびSFTP サーバーのアップグレード

AdobeのFTPおよびSFTP サーバーをアップグレードすると、一部のサーバー設定に依存して構築されることが多いオートメーションスクリプト（データを定期的にダウンロードまたはアップロードするために頻繁に使用される）に影響を与える新しい設定が生じる可能性があります。

例えば、新しい成功ステータスが導入され、成功ステータスを使用して特定のアクションをトリガーするスクリプトに影響を与えます。 Adobeは、このような設定の変更をユーザーにプロアクティブに通知します。 FTP サーバーのアップグレードが差し迫っていることをAdobeから通知された場合は、オートメーションスクリプトが正しく動作していることを確認します。
