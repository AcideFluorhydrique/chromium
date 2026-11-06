# Chromium CI 分支

這個分支只放 GitHub Actions workflow，原始碼在執行時從 chromium.googlesource.com 抓。

`Build Chromium Android (relay)`：免費 runner 單一 job 最多 6 小時，
所以拆成最多 6 個 stage 接力編譯 `chrome_public_apk`，每棒用 artifact 傳遞進度，
編完的那一棒上傳 APK。

用法：把這個分支設成 repo 的預設分支（workflow_dispatch 只會讀預設分支上的 workflow）。
