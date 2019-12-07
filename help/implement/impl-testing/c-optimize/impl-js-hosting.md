---
description: ページの最上部に JavaScript ライブラリファイルの呼び出しを配置すると、ダウンロードされる最初の要素にイメージが必ず含まれるようになります。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: JavaScript ファイルの場所と並行処理
topic: Developer and implementation
uuid: ed5118a8-b142-4fab-8aa1-92d931cc1439
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# JavaScript ファイルの場所と並行処理

ページの最上部に JavaScript ライブラリファイルの呼び出しを配置すると、ダウンロードされる最初の要素にイメージが必ず含まれるようになります。

ほとんどの Web ブラウザーはイメージを同時にダウンロードします。通常、3 ～ 4 個のイメージを同時にダウンロードできます。

ほとんどの Web ブラウザーは要素を同時にダウンロードするので、一般的な多くのブラウザー（Internet Explorer など）のステータスバーでは、ブラウザーが読み込もうとしている要素が正しく反映されません。例えば、ステータスバーに、ブラウザーがイメージ 1 のダウンロードを待機していることがレポートされる場合があります。これに対して、ネットワークパケットテストでは、ブラウザーがイメージ 1 を既に受信し、現在はイメージ 2 を待機していることが示されます。

> [!NOTE]サードパーティのインターネットパフォーマンス監査プロバイダー（Keynote Systems など）はページのイメージ要素を同時ではなく順番にダウンロードするので、一般的なユーザーエクスペリエンスが再現されません。

