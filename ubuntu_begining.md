# ubuntu-开箱配置
## 系统设置
### change ppa
The configuration file of the software source on ubuntu is /etc/apt/sources.list<br/>
And the configuration should be copied ( you'd better do it before you chang any configuration file
in case that you recover it).<br/>
Then you can do the following:<br/>
<pre>
  # 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
  # 预发布软件源，不建议启用
  # deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
  # deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
</pre>
### enable canonical partner
sudo add-apt-repository "deb http://archive.canonical.com/ $(lsb_release -sc) partner"<br>
sudo add-apt-repository "deb http://extras.ubuntu.com/ubuntu raring main"<br>
sudo apt-get update<br>
### system language
if you install ubuntu with chinese language, you will find that the dir are "桌面 文档” etc...   
It is diffcult to chang directory.    
You can do the following:     
* change the system language into english     
* reboot    
* change the system language into chinese    
* reboot     
* at the beginning, ubuntu will remind you if you want to chang directoy name, choose "否“    
### start ipv6
sudo apt install miredo    
sudo gedit /etc/default/ufw   
* change "ipv6=no" into "ipv6=yes" (maybe you should try many times )    
sudo ufw disable     
sudo ufw enable    
### 双系统时间问题
timedatectl set-local-rtc 1   
### 更换终端类型(ob-my-zsh)
sudo apt install zsh zsh-completions curl <br/>
chsh -s /bin/zsh  <br/>
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"    <br/>
sudo apt install autojump   <br/>
vim ~/.zshrc
        plugins=(git autojump)
### prevent overheating
TLP:power managerment tool<br>
sudo add-apt-repository ppa:linrunner/tlp<br>
sudo apt-get update<br>
sudo apt-get install tlp tlp-rdw<br>
### touchpad
sudo apt install libinput-tools<br/>
sudo apt-get install xdotool<br/>
sudo gem install fusuma<br/>
and then you must configure the gestures and website[website](https://italolelis.com/posts/multitouch-gestures-ubuntu-fusuma/)

## 软件安装
### git
sudo apt install git
### atom
download atom  [atom](https://atom.io/ "atom")     
### chrome
download chrome [chrome](https://www.chrome64bit.com/index.php/google-chrome-64-bit-for-linux "chrome")     
### emacs
sudo apt update         
sudo apt install emacs  
### virtualbox
sudo apt install virtualbox 
### deepin-wine
git clone https://github.com/HarryPotterJackson/deepin-wine-ubuntu.git    
./install.sh
### software-deepend-deepin-wine
http://mirrors.aliyun.com/deepin/pool/non-free/d/     
### vim
sudo apt update    
sudo apt install vim    
### gnome-tweak-tool
sudo apt install gnome-tweak-tool     
### popup-dict(dirctionary)
sudo apt install python3-pip   
sudo apt install python-gi python-gi-cairo python3-gi python3-gi-cairo gir1.2-gtk-3.0      
sudo pip3 install popupdict    
### gnome拓展
sudo apt install chrome-gnome-shell
### wps
download wps for linux [wps](http://community.wps.cn/download/ "wps_for_linux")   
### remarkable
download remarkable for linux [remarkable](http://remarkableapp.github.io/ "remarkable")   
### zeal
sudo apt install zeal     
### gitkraken
https://www.gitkraken.com/
### lantern
download lantern [lantern](https://github.com/HarryPotterJackson/lantern "lantern for linux")    
### chinese input
sudo apt install fcitx     
https://pinyin.sogou.com/linux/?r=pinyin       
