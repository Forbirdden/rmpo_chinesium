---
title: TECNO POVA 6 Neo
category: Устройства
order: 10
icon: smartphone
description: Довольно популярный 7к мах кирпич от Transsion, MediaTek Helio G99 Ultimate (MT6789)
---

# Стоковая прошивка
## LI6-15.1.2.155 (OP001PF001AZ)
<a href="https://archive.org/download/hios-li6-15.1.2.155-op001pf001az/Tecno-Pova-6-Neo-Li6-15.rar" target="_blank" rel="noopener">
  <md-button variant="outlined">Скачать</md-button>
</a>

### Отдельные файлы из этой версии
<a href="https://archive.org/download/20261106_20261106_1833/boot.img" target="_blank" rel="noopener">
  <md-button variant="outlined">Скачать boot.img</md-button>
</a>
<a href="https://archive.org/download/20261106_20261106_1833/vbmeta.img" target="_blank" rel="noopener">
  <md-button variant="outlined">Скачать vbmeta.img</md-button>
</a>

# Разблокировка загрузчика официально
- Войдите в TECNO ID
- Включите отладку по USB и заводскую разблокировку в настройках разработчика
- При подключении к ПК разрешите отладку
- Перезагрузка в ***Fastboot***
```bash
adb reboot bootloader
```
- Разблокировка, после того как на экране появится голубой кабель и надпись FASTBOOT
```bash
fastboot flashing unlock
```
- Отключение dm-verity
```bash
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
```

# APatch
Root права на уровне ядра с простой установкой

- Прошивка патченного boot.img
<a href="https://archive.org/download/20261106_20261106_1833/apatch_li6.img" target="_blank" rel="noopener">
  <md-button variant="outlined">Скачать пропатченный мной boot</md-button>
</a>

Пропатчить самостоятельно можно в приложении APatch

Прошивка в ***FastbootD***
```bash
fastboot flash boot apatch_li6.img
```

# LineageOS GSI с патчами TrebleDroid
LineageOS с с популярными патчами "TrebleDroid" под различное железо

Сделано MisterZtr

## 23.2 2026.05.24 Vanilla EROFS
Без Google сервисов, система только для чтения

<a href="https://sourceforge.net/projects/misterztr-gsi/files/LineageOS/Android%2016/LineageOS-23.2-20260524-VANILLA-EROFS-GSI.7z/download" target="_blank" rel="noopener">
  <md-button variant="outlined">LineageOS-23.2-20260524-VANILLA-EROFS-GSI.7z</md-button>
</a>

- Освобождение места под прошивку в ***FastbootD***
```bash
fastboot erase product
```
```bash
fastboot resize-logical-partition product 0x0
```

- Прошивка в ***FastbootD*** распакованного из архива образа
```bash
fastboot flash system "LineageOS-23.2-20260524-VANILLA-EROFS-GSI.img"
```

# PitchBlack Recovery Project
Прошивается в раздел vendor_boot

<a href="https://github.com/PitchBlackRecoveryProject/android_device_TECNO_LI6-pbrp/releases/latest" target="_blank" rel="noopener">
  <md-button variant="outlined">GitHub</md-button>
</a>

- Прошивка в ***Fastboot***
```bash
fastboot flash vendor_boot vendor_boot.img 
```
