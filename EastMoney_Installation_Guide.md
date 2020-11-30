# Install wine from APT
`sudo apt install wine`

# setup wine env, skip this if you already have one
`export WINEARCH=win32`
`export WINEPREFIX=~/.wine32`

# setup and config wine
`winecfg`

# Install WineTricks
`sudo apt install winetricks`

# install some wine conponents
`winetricks corefonts gdiplus riched20 riched30 wenquanyi ie8 vcrun2008 d3dx9 ole32`

## Optional: some conponents may not be avaliable depanding on your network environment, Download them via proxy first, and copy to winetricks cache dir.

# Config wine regedit
Download this [.reg](https://gist.github.com/swordfeng/c3fd6b6fcf6dc7d7fa8a) file.
Open regedit with the command:
`winetricks regedit`
In the Menu bar, click Registry and select Import Registry File…

# Download EastMoney
Download from [EastMoney](https://www.eastmoney.com/) official

# Run installer with wine
`env LANG=zh_CN.UTF-8 wine <THE FILE PATH YOU JUST DOWNLOADED>`
wine should create some shortcuts in your appliaction menu

# Edit shortcuts
add `LANG=zh_CN.UTF-8` to the shortcuts target after `env`