                Archlinux installation

    
    connect network use iwctl or nmtui
    mkfs.fat -F32 /dev/nvme0n1p1
    mkfs.ext4 /dev/nvme0n1p2
    mount /dev/nvme0n1p2 /mnt
    mkdir /mnt/boot
    mount /dev/nvme0n1p1 /mnt/boot
    archinstall..
------------------------------------------------------------------------------------------------------------------------------------------
                GUI setting
 screen resolution customize: `arandr`                          
 custom audio PulseAudio                 `pavucontrol`                  
 network:                    `nm-connection-editor`, `nmtui`                                    
 filemanager: nautilus / dophin
 Del file terminal file manager-> sudo ncdu / (with intuitive gui)
 
------------------------------------------------------------------------------------------------------------------------------------------
                Network

    iwctl
    station wlan0 scan on
    station wlan0 get-network
    station wlan0 connect wifi-name

or use nmtui (install networkmanager,enable & start NetworkManager)
------------------------------------------------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------------------------------------------------
CLeanup (optional)
1. Tìm thư viện không còn được dùng (orphans)
  
  sudo pacman -Qdt

→ Liệt kê các gói cài làm phụ thuộc, nhưng hiện không còn cần nữa.
 2. Xóa các gói orphan
  
  sudo pacman -Rns $(pacman -Qdtq)

Điều này sẽ:

    Gỡ các gói không cần nữa

    Gỡ luôn file trong /usr/lib của gói đó

-Unistall -> 
  +del orphan: sudo pacman -Rns $(pacman -Qdtq)
  +del old cache: sudo paccache -r
  +Unistall installed software: ex: pacman -Q | grep -Ei 'i3|bspwm|xmonad|qtile|awesome|dwm|hyprland|sway'
                                ex: sudo pacman -Rns i3-wm bspwm awesome (-R: remove  -n: remove config files installed by package  -s: remove unused dependencies installed with the package)
