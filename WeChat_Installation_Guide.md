# setup env same as [EastMoney](https://github.com/BolunHan/Wine--/blob/main/EastMoney_Installation_Guide.md)
and install WeChat.exe
can be installed into same wineprefix as EastMoney, but only need riched20 wenquanyi override

## variant
add following lines to env
```
export GTK_IM_MODULE="fcitx"
export QT_IM_MODULE="fcitx" 
export XMODIFIERS="@im=fcitx"
```
