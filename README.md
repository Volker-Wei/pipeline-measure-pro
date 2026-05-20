# 管溝丈量系統 PWA GitHub Pages 部署包

## 這包檔案用途

這是依照你目前 GitHub 裡的檔案整理出的 PWA 版本，保留：

- `index.html`
- `manifest.json`
- `icons/wrench-180.png`
- `icons/wrench-192.png`

另外補上：

- `service-worker.js`
- `icons/wrench-512.png`
- `icons/wrench-maskable-512.png`
- `.well-known/assetlinks.json` 範本

## 建議放置位置

GitHub Pages 專案：

```text
pipeline-measure-pro/
├─ index.html
├─ manifest.json
├─ service-worker.js
└─ icons/
   ├─ wrench-180.png
   ├─ wrench-192.png
   ├─ wrench-512.png
   └─ wrench-maskable-512.png
```

你的網站網址：

```text
https://volker-wei.github.io/pipeline-measure-pro/
```

## Android TWA 注意

如果要讓 Android APK 用 TWA 完整全螢幕開啟，`assetlinks.json` 必須放在網域根目錄：

```text
https://volker-wei.github.io/.well-known/assetlinks.json
```

不是：

```text
https://volker-wei.github.io/pipeline-measure-pro/.well-known/assetlinks.json
```

所以建議另外建立 `volker-wei.github.io` repository，並把 `.well-known/assetlinks.json` 放進去。

## Android 簽章後需要改 assetlinks

`assetlinks.json` 裡面的 SHA-256 目前是佔位文字。你用 Android Studio 產生簽章後，要把 SHA-256 憑證指紋填進去。
