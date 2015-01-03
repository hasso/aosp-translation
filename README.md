AOSP Androidi tõlge eesti keelde
================================

Käesolev on varases beeta staadiumis eesti keele tõlge Android süsteemile. Töö toimub alati viimase AOSP stabiilse haru peal.

Tõlke kasutamine oleks OVERLAY süsteemi kasutades lihtne ka suuremaid muudatusi lähtetekstis tegemata, kuid paraku on Androidi kompileerimise süsteemis [bugi](https://code.google.com/p/android/issues/detail?id=60586), mis selle välistab. Hetkel on parim võimalus lihtsalt sellest tõlke repost endale koopia tekitada ning Androidi keeleressursside failid selles repos olevatega üle kirjutada:

    $ for f in $(find . -name *.xml); do cp $f $ANDROID_SOURCE/$f; done

Edasi kompileeri Androidi süsteem kokku nagu tavaliselt.

AOSP Android translation to Estonian
====================================

This is a early beta of AOSP Android translation to Estonian in form of overlay, so it can be used to build system ROM's. Although this translation is already much better than the one in AOSP, it's recommended to use it only if you are interested in reporting problems and/or contributing.
