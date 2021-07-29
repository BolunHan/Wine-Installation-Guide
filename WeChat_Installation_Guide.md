# Reuse [EastMoney](https://github.com/BolunHan/Wine--/blob/main/EastMoney_Installation_Guide.md) prefix
just run WeChatSetup.exe and config the shortcuts

---

# Fresh setup

## Step 0: install PlayOnLinux and setup fresh wine32 5.0 prefix

Install wine5.0 x86 using PoL. The env should be placed at default location `~/.PlayOnLinux/wine/linux-x86/5.0/bin/wine`

This example names the prefix as `WeChat` and places it at default location `~/.PlayOnLinux/wineprefix/WeChat`


## Step 1: Override riched20 wenquanyi with winetricks

Install overrides with `env WINE=~/.PlayOnLinux/wine/linux-x86/5.0/bin/wine WINEPREFIX=~/.PlayOnLinux/wineprefix/WeChat winetricks riched20 wenquanyi cjkfonts`


## Step 2: Download and Install WeChat

Download WeChat setup with `wget https://dldir1.qq.com/weixin/Windows/WeChatSetup.exe WeChatSetup.exe`

Install WeChat with `env WINEPREFIX=~/.PlayOnLinux/wineprefix/WeChat ~/.PlayOnLinux/wine/linux-x86/5.0/bin/wine WeChatSetup.exe`


## Step 3: Config ShortCuts

If setup runs smoothly, a shortcut should be created at `~/.local/share/applications/wine/Programs/WeChat/WeChat.desktop`

Edit the .desktop file and add `LANG="zh_CN.UTF-8"` after `Exec=env`

Change `Exec=env ... wine ...` into `Exec=env ... ~/.PlayOnLinux/wine/linux-x86/5.0/bin/wine ...`


## Step 4: config input method

If using fcitx as input method, add following environment variables

```
GTK_IM_MODULE="fcitx"
QT_IM_MODULE="fcitx"
XMODIFIERS="@im=fcitx"
```

## Step 5: override font with M$yh

Download and unzip [Uploading fake_simsun.zip…](Fake Simsun) font file and place it in `$WINEPREFIX/drive_c/windows/Fonts/`
