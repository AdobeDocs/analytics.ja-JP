---
title: 音声分析ディメンション
description: 音声分析ディメンション
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# 音声分析ディメンション

[!UICONTROL &#x200B; アプリケーションレポート &#x200B;] で [[!UICONTROL &#x200B; 音声およびチャットボット &#x200B;]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md) を有効にすると、次のディメンション（および [&#x200B; 指標 &#x200B;](../metrics/voice-metrics.md)）が作成されます。 [&#x200B; コンテキストデータ変数 &#x200B;](/help/implement/vars/page-vars/contextdata.md) を使用して、目的の文字列値に設定できます。 レポートスイートの設定で有効にすると、音声分析ディメンションを関連するコンテキストデータ変数にマッピングする [&#x200B; 処理ルール &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) が自動的に作成されます。

| ディメンション名 | 説明 | コンテキストデータ変数 |
| --- | --- | --- |
| 音声エラータイプ | 発生したエラーのタイプ。 | `a.voiceerrortype` |
| 音声言語 | ユーザーが音声アプリでやり取りする言語。 | `a.voicelanguage` |
| 音声インテント | ユーザーが実行するコマンド。 | `a.voiceintent` |
| 音声アプリの応答 | 音声アプリがユーザーに返した応答。 | `a.voiceappresponse` |
| 音声認証 | 音声アプリとやり取りする際のユーザーの認証状態。 | `a.voiceauthentication` |
| 目標点 ID | 目標点 ID。 | `a.loc.poi.id` |

{style="table-layout:auto"}
