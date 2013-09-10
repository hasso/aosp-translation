Androidi tõlge eesti keelde
===========================

Käesolev on varases beeta staadiumis eesti keele tõlge Android süsteemile. Töö toimub CyanogenMod 10.1 (Android 4.2.2) stabiilse
süsteemi peal, kuid tõlge sobib kasutamiseks ka teistes Android 4.2 süsteemides, mis võimaldavad lähtetekstidest
kompileerimist (nt AOSP).

Selle tõlke kasutamiseks tuleb teha järgmist:

1. Lisa tõlke repo lokaalsete manifestide hulka. Selleks tekita Androidi lähtetekstide kataloogi `.repo/local_manifests/et-translation.xml` fail, mille sisu on järgmine: 

        <?xml version="1.0" encoding="UTF-8"?>
        <manifest>
          <project name="..." path="vendor/ht/et-translation"/>
        </manifest>

  Ning anna seejärel käsk `repo sync`. 

2. Lisa eesti keel süsteemi lisatavate keelte hulka. Selleks lisa eesti keel (kood *et_EE*) `build/target/product/languages_full.mk` failis `PRODUCT_LOCALES` muutujas defineeritud keelte hulka.

3. Ütle kompileerimissüsteemile, et sinu seadme puhul tuleb kasutada just selle tõlke ressursifaile. Selleks tuleb lisada vendor/ht/et-translation repo konkreetse seadme _overlay'de_ hulka. Näiteks minu Nexus 4 (koodnimi _mako_) puhul tuleb seda teha failis `device/lge/mako/device.mk`, mudida seal muutujat `DEVICE_PACKAGE_OVERLAYS` ning vastav sektsioon näeb pärast seda välja selline:

        DEVICE_PACKAGE_OVERLAYS := device/lge/mako/overlay \
                                   vendor/ht/et-translation
  
Edasi kompileeri Androidi süsteem kokku nagu tavaliselt.

Android (CyanogenMod + AOSP) translation to Estonian
====================================================

This is a early beta of Android (CyanogenMod 10.1 + AOSP 4.2.2) translation to Estonian in form of overlay, so it can be used to build system ROM's. Although this translation is already much better than the one in AOSP, it's recommended to use it only if you are interested in reporting problems and/or contributing.
