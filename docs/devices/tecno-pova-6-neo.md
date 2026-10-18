---
title: TECNO POVA 6 Neo
category: Устройства
order: 10
icon: smartphone
badge: MediaTek Helio G99 Ultimate (MT6789)
description: Довольно популярный 7к мах кирпич от Transsion
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
- Перезагрузка в Fastboot
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

Подразумевая что вы только что отключили dm-verity перезагрузитесь в FastbootD
```bash
fastboot reboot fastboot
```

- Прошейте патченный boot.img
Можно пропатчить самостоятельно, загрузив boot.img из прошивки в приложение APatch
А можно прошить мой:

<a href="https://files.catbox.moe/vrbg0r.img" target="_blank" rel="noopener">
  <md-button variant="outlined">boot.img с APatch</md-button>
</a>

```bash
fastboot flash boot vrbg0r.img
```

# LineageOS GSI 23.2 с патчами TrebleDroid
Спасибо MisterZtr за [LineageOS GSI](https://github.com/MisterZtr/LineageOS_gsi)
Тестировал только одну версию:
## 2026.05.24 Vanilla EROFS
Без Google сервисов, система только для чтения

- Скачайте архив с прошивкой
<a href="https://sourceforge.net/projects/misterztr-gsi/files/LineageOS/Android%2016/LineageOS-23.2-20260524-VANILLA-EROFS-GSI.7z/download" target="_blank" rel="noopener">
  <md-button variant="outlined">LineageOS-23.2-20260524-VANILLA-EROFS-GSI.7z</md-button>
</a>

- Распакуйте .img образ

- В FastbootD освободите место под прошивку
```bash
fastboot erase product
```
```bash
fastboot resize-logical-partition product 0x0
```

- Прошейте LineageOS GSI 23.2
```bash
fastboot flash system "LineageOS-23.2-20260524-VANILLA-EROFS-GSI.img"
```
