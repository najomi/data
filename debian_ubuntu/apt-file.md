С помощью apt-file можно быстро узнать в каком пакете хранится необходимый
заголовочный файл  или нужный бинарник:
```sh
sudo apt-file update
apt-file search Xft.h
# libghc-x11-xft-dev: /usr/lib/haskell-packages/ghc/lib/X11-xft-0.3.1/ghc-7.6.3/Graphics/X11/Xft.hi
# libghc-x11-xft-doc: /usr/share/doc/libghc-x11-xft-doc/html/Graphics-X11-Xft.html
# libghc-x11-xft-doc: /usr/share/doc/libghc-x11-xft-doc/html/mini_Graphics-X11-Xft.html
# libghc-x11-xft-doc: /usr/share/doc/libghc-x11-xft-doc/html/src/Graphics-X11-Xft.html
# libxft-dev: /usr/include/X11/Xft/Xft.h
apt-file search /dmenu
# herbstluftwm: /usr/share/doc/herbstluftwm/examples/dmenu.sh
# pianobar: /usr/share/doc/pianobar/contrib/eventcmd-examples/dmenu.pl
# suckless-tools: /usr/bin/dmenu.default
# suckless-tools: /usr/bin/dmenu.xft
# suckless-tools: /usr/bin/dmenu_run
# suckless-tools: /usr/share/man/man1/dmenu.default.1.gz
# suckless-tools: /usr/share/man/man1/dmenu.xft.1.gz
# suckless-tools: /usr/share/man/man1/dmenu_run.1.gz
# uzbl: /usr/share/uzbl/examples/data/scripts/util/dmenu.sh
```


