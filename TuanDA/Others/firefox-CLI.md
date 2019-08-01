cd /usr/local
    2  wget http://ftp.mozilla.org/pub/firefox/releases/67.0/linux-x86_64/en-US/firefox-67.0.tar.bz2
    3  tar xvjf firefox-67.0.tar.bz2
    4  tar xvjf firefox-67.0.tar.bz2 
    5  yum install bzip2
    6  tar xvjf firefox-67.0.tar.bz2 
    7  sudo ln -s /usr/local/firefox/firefox /usr/bin/firefox
    8  yum install  xorg-x11-server-Xorg xorg-x11-xauth xorg-x11-apps -y


    9  reboot
   10  xclock
   11  vim /etc/ssh/sshd_config
   12  vi /etc/ssh/sshd_config
   13  service sshd restart
   14  ip a
   15  reboot
   16  yum install  xorg-x11-server-Xorg xorg-x11-xauth xorg-x11-apps
   17  vi /etc/ssh/sshd_config 
   1. Uncomment the following lines:

X11Forwarding yes
X11DisplayOffset 10
X11UseLocalhost no

   18  systemctl restart sshd.service
   19  xclock
   20  /usr/bin/firefox &
   21  /usr/bin/firefox www.cyberciti.biz
   22  firefox --new-tab url
   23  type -a firefox
   24  /usr/bin/firefox
   25  ls -la /usr/local/firefox/libmozgtk.so
   26  export LD_LIBRARY_PATH=/usr/lib64:$LD_LIBRARY_PATH
   27  /usr/bin/firefox
   28  firefox &
   29  reboot
   30  firefox &
   31  tail -200 /var/log/messages 
   32  firefox &
   33  ls /usr/local/firefox/libmozgtk.so
   34  yum install gtk3
   35  firefox &
   36  top -c
   37  free -m
   38  ls -la
   39  ls -la /usr/local/
   40  wget https://download.mozilla.org/?product=firefox-latest-ssl&os=linux64&lang=en-US
   41  history
   42  top -c
   43  firefox
   44  firefox &




   ubuntu
   17  vi /etc/ssh/sshd_config 
   1. Uncomment the following lines:

X11Forwarding yes
X11DisplayOffset 10
X11UseLocalhost no