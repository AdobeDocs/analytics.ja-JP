---
description: 新しいバージョンの JavaScript AppMeasurement では、サポートされるプラグインが変更されました。
keywords: Analytics Implementation;appmeasurement;javascript;plugin;plug-in
subtopic: JavaScript AppMeasurement
title: AppMeasurement プラグインのサポート
topic: Developer and implementation
uuid: e048e16b-994a-4079-bde4-3faa3df8c96d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# AppMeasurement プラグインのサポート

現在のバージョンの JavaScript AppMeasurement でのプラグインサポート。

## 検証済みのプラグイン {#section_48415FB895E6455FAC34B0B96DE6EBE7}

次のプラグインについては検証をおこない、互換性が確認されています。

* [s.abort フラグ](/help/implement/js-implementation/plugins/abort.md)
* [appendList](/help/implement/js-implementation/plugins/appendlist.md)
* [doPlugins 関数](/help/implement/js-implementation/plugins/function-doplugins.md)
* [getAndPersistValue](/help/implement/js-implementation/plugins/getandpersistvalue.md)
* [getDaysSinceLastVisit](/help/implement/js-implementation/plugins/getdayssincelastvisit.md)
* [getLoadTime](/help/implement/js-implementation/plugins/getloadtime.md)
* [getNewRepeat](/help/implement/js-implementation/plugins/getnewrepeat.md)
* [getPageVisibility](/help/implement/js-implementation/plugins/pagevisibility.md)
* [getPercentPageViewed](/help/implement/js-implementation/plugins/getpercentpageviewed.md)
* [getPreviousValue](/help/implement/js-implementation/plugins/getpreviousvalue.md)
* [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md)
* [getTimeParting](/help/implement/js-implementation/plugins/gettimeparting.md)
* [getValOnce](/help/implement/js-implementation/plugins/getvalonce.md)
* [getVisitNum](/help/implement/js-implementation/plugins/getvisitnum.md)
* [getVisitStart](/help/implement/js-implementation/plugins/getvisitstart.md)
* [hitGovernor](/help/implement/js-implementation/plugins/hitgovernor.md)
* [内部トラフィック](/help/implement/js-implementation/plugins/internal-traffic.md)
* [performanceTiming](/help/implement/js-implementation/plugins/performancetiming.md)
* [trackTNT](/help/implement/js-implementation/plugins/tracktnt.md)

## 検証されていないプラグイン {#section_32BA7CAB37554A278170A728F1D65CE9}

次のプラグインは、基礎となる機能はサポートされているので引き続き動作しますが、互換性の検証および確認はおこなわれていません。移行前に、開発環境でこれらのプラグインの動作を確認する必要があります。

* getActionDepth
* getCookiesAccepted
