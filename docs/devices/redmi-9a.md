---
title: Redmi 9A
category: Устройства
order: 10
icon: smartphone
description: Очень распространённый ультрабюджетник, MediaTek Helio G25 (MT6762G)
---

# Стоковая прошивка
## MIUI V12.5.7.0.RCDMIXM Global
<a href="https://bn.d.miui.com/V12.5.7.0.RCDMIXM/dandelion_global_images_V12.5.7.0.RCDMIXM_20221107.0000.00_11.0_global_3319fae180.tgz" target="_blank" rel="noopener">
  <md-button variant="outlined">Скачать</md-button>
</a>

# Разблокировка загрузчика через BootROM
Нужен mtkclient

- Запустите разблокировку загрузчика
```bash
python mtk.py da seccfg unlock
```

- На выключенном телефоне зажмите громкость вверх + питание, быстро подключите кабель к компьютеру
На какой-нибудь там десятитысячной попытке точно получится

# Kitsune Mask
Root права, поддержка прекращена

- Пропатчить в приложении Kitsune Mask стоковый boot.img

- Прошивка в ***FastbootD*** патченного boot.img
```bash
fastboot flash boot boot.img
```

# TrebleDroid
Популярная GSI прошивка с патчами под различное железо

## android_14.0.0_r17 ci-20240105 Vanilla EXT4
Без Google сервисов

<a href="https://github.com/TrebleDroid/treble_experimentations/releases/download/ci-20240105/system-td-arm32_binder64-ab-vanilla.img.xz" target="_blank" rel="noopener">
  <md-button variant="outlined">Скачать system-td-arm32_binder64-ab-vanilla.img.xz</md-button>
</a>

- Прошивка в ***FastbootD*** распакованного из архива образа
```bash
fastboot flash system "system-td-arm32_binder64-ab-vanilla.img"
```

# OrangeFox Recovery Project

<a href="https://orangefox.download/release/62bb16c36a44bc738419d9bb" target="_blank" rel="noopener">
  <md-button variant="outlined">Скачать</md-button>
</a>

- Прошивка в ***Fastboot*** распакованного из архива образа
```bash
fastboot flash recovery recovery.img 
```
