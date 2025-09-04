# Install vim-7.4 on Debian

```
apt-get update
apt-get install build-essential libncurses-dev git
cd /usr/local/src
wget https://github.com/vim/vim/archive/refs/tags/v7.4.tar.gz -O vim-7.4.tar.gz
tar -xzvf vim-7.4.tar.gz
cd vim-7.4
CFLAGS="-DSYS_VIMRC_FILE='\"/etc/vim/vimrc\"' -DSYS_GVIMRC_FILE='\"/etc/vim/gvimrc\"'" ./configure \
  --prefix=/usr/local \
  --with-features=huge \
  --enable-multibyte \
  --disable-gui \
  --disable-luainterp \
  --disable-perlinterp \
  --disable-rubyinterp \
  --disable-pythoninterp \
  --disable-python3interp \
  --enable-cscope \
  --with-tlib=ncurses \
  --enable-fail-if-missing
make
make install
wget https://raw.githubusercontent.com/anzz1/vimconfig/master/vim74/debian.vim -O /usr/local/share/vim74/debian.vim
wget https://raw.githubusercontent.com/anzz1/vimconfig/master/colors/less.vim -O /usr/local/share/vim74/colors/less.vim
wget https://raw.githubusercontent.com/anzz1/vimconfig/master/vimrc -O /etc/vim/vimrc
wget https://raw.githubusercontent.com/anzz1/vimconfig/master/vimrc.local -O /etc/vim/vimrc.local
```
