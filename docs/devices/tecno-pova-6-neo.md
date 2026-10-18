---
title: TECNO POVA 6 Neo
category: Устройства
order: 10
icon: smartphone
description: Довольно популярный 7к мах кирпич от Transsion, MediaTek Helio G99 Ultimate (MT6789)
---

# Стоковая прошивка
## LI6-15.1.2.155 (OP001PF001AZ)
Спасибо aimrite2

<a href="https://drive.google.com/file/d/1wKcVk1iP6PpE8TgpKIujFTfy4JTMXvHX/view" target="_blank" rel="noopener">
  <md-button variant="outlined">Google Drive</md-button>
</a>

### Отдельные файлы из этой версии
<a href="https://files.catbox.moe/u4mwdw.img" target="_blank" rel="noopener">
  <md-button variant="outlined">boot</md-button>
</a>
<a href="https://files.catbox.moe/mpa7vx.img" target="_blank" rel="noopener">
  <md-button variant="outlined">vbmeta</md-button>
</a>

# Разблокировка загрузчика
Лично я разблокировл официально, mtkclient не тестировал
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
- Отключение dm-verity (нужен vbmeta из прошивки)
```bash
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
```

# APatch
Root права

- Прошивка патченного boot.img
<a href="https://files.catbox.moe/vrbg0r.img" target="_blank" rel="noopener">
  <md-button variant="outlined">Пропатченный мной boot</md-button>
</a>

Пропатчить самостоятельно можно в приложении APatch

Прошивка в ***FastbootD***
```bash
fastboot flash boot vrbg0r.img
```

# LineageOS GSI с патчами TrebleDroid
Спасибо MisterZtr

Я тестировал только одну версию:

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

- Прошивка
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
