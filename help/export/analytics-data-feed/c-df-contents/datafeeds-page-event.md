---
description: page_event の値に基づいてヒットタイプを判別する参照テーブル。
keywords: Data Feed;page;event;page_event;post_page_event
title: ページイベント参照
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ページイベント参照

page_event の値に基づいてヒットタイプを判別する参照テーブル。

| ヒットタイプ | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| ページビュー | 0:モバイルSDKの `trackState` | 次と同じ値 `post_page_event` |
| リンクトラッキング | 10:モバイルSDK' `trackAction` s<br>11のカスタムリンクと呼び出し：ダウンロード<br>リンク12:離脱リンク | 100:モバイルSDK' `trackAction` s<br>101のカスタムリンクと呼び出し：ダウンロード<br>リンク102:離脱リンク |
| マイルストーンビデオ | 31:メディア<br>開始32:メディアの更新（他の変数処理なし）<br>33:メディアの更新（他の変数を使用） | 76:メディア<br>開始77:メディアの更新（他の変数処理なし）<br>78:メディアの更新（他の変数を使用） |
| ハートビートビデオ | 50:メディアストリーム開始（Primetime以外）<br>51:メディアストリーム終了（Primetime以外）<br>52:メディアストリームスクラブ（Primetime以外）<br>53:メディアストリームキープアライブ（Primetime以外）<br>54:メディアストリーム広告開始（Primetime以外）<br>55:メディアストリーム広告終了（Primetime以外）<br>56:メディアストリーム広告スクラブ（Primetime以外）<br>60:Primetimeメディアストリーム<br>start61:Primetimeメディアストリーム<br>close62:Primetimeのメディアストリームスクラブ<br>63:Primetimeのメディアストリームkeep alive<br>64:Primetimeメディアストリーム広告<br>開始65:Primetimeメディアストリーム広告<br>close66:Primetimeのメディアストリーム広告スクラブ | 次と同じ値 `post_page_event` |
| 調査 | 40:Surveyから生成された任意の呼び出し | 80:Surveyから生成された任意の呼び出し |
| Analytics for Target | 70:ヒットにTargetアクティビティデータが含まれる | 次と同じ値 `post_page_event` |
