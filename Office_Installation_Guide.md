# Install wine from APT, this method is tested on wine 5.0.3 (wine-stable)
`sudo apt install wine`

# setup wine env, skip this if you already have one
`export WINEARCH=win32` <br>
`export WINEPREFIX=~/.office2013`

# setup and config wine
`winecfg`

# Install WineTricks
`sudo apt install winetricks`

# install some wine conponents
`winetricks rich2 usp10 msxml6 richtx32 msftedit vb6run`

# Download [office 2013 retail](ed2k://|file|en_office_professional_plus_2013_x86_dvd_1123673.iso|699004928|BB00273C2DA5FF775165D748DBFDA37C|/)
mount the iso, then run setup.exe with wine

#optional: activate with a key
