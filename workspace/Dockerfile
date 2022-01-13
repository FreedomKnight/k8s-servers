from fedora:latest

# System 
run dnf install -y passwd git composer vim tmux java-latest-openjdk java-latest-openjdk-devel php nodejs  
run useradd -s /bin/bash FreedomKnight && usermod -aG wheel FreedomKnight && passwd -d FreedomKnight

# Personal 
add https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim /home/FreedomKnight/.vim/autoload/plug.vim 
add https://raw.githubusercontent.com/FreedomKnight/configuations/master/vimrc /home/FreedomKnight/.vimrc 
add https://raw.githubusercontent.com/FreedomKnight/configuations/master/package.json /home/FreedomKnight/.config/coc/extensions/package.json

run chown -R FreedomKnight:FreedomKnight /home/FreedomKnight/.vim /home/FreedomKnight/.vimrc /home/FreedomKnight/.config/

# Setup vim
run sudo -u FreedomKnight vim -c PlugInstall -c qa
run cd /home/FreedomKnight/.config/coc/extensions/ && sudo -u FreedomKnight npm install coc-git coc-go coc-java coc-java coc-phpls coc-tsserver coc-vetur coc-yaml --global-style --ignore-scripts --no-bin-links --no-package-lock --only=prod

workdir /home/FreedomKnight
user FreedomKnight
