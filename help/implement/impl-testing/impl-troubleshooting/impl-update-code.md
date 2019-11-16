---
description: 既存の Analytics コードを更新するためのベストプラクティスがいくつかあります。
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Analytics コードの置き換え
topic: Developer and implementation
uuid: d3ea6585-199f-4dbe-9ee8-15b204689f2f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analytics コードの置き換え

既存の Analytics コードを更新するためのベストプラクティスがいくつかあります。

多くの場合、お客様がアドビの[!UICONTROL コードマネージャー]を使用して最新バージョンのコードに置き換えます。特定の事項に留意すれば、この方法がお勧めです。

## 不正なデータ収集サーバー ID の使用 {#section_1726CEB1ABEC408492569B06664410C8}

アドビのコードマネージャーから生成されたものではない汎用の [!DNL s_code.js] ファイルが、サイトにコードを導入するファイルに送信される場合があります。その結果、アカウントに対して不正なデータ収集サーバー ID（[!UICONTROL s.dc] 変数に示される）が使用されます。別のレポートスイートのコードを再利用するのではなく、特定のレポートスイート用の新しいコードを[!UICONTROL コードマネージャー]から直接生成することをお勧めします。[!UICONTROL s.dc] 変数を正しく入力するには、これが最適な方法です。

## プラグイン {#section_53650E52D6A54A4795F95E491E7548D1}

アドビ製品の機能を強化するために、プラグインを導入する場合があります。コードを置き換える際は、そのコードにプラグインを含めることを忘れないようにしてください。[!UICONTROL コードマネージャー]で作成されたコードにはプラグインコードが含まれていないので、すべてのプラグインを新しいコードベースに手動で移行する必要があります。念のため既存のコードをコピーし、元の状態に戻せるようにしておいてください。
