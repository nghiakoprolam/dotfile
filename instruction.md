                Archlinux installation
    connect network use iwctl
    mkfs.fat -F32 /dev/nvme0n1p1
    mkfs.ext4 /dev/nvme0n1p2
    mount /dev/nvme0n1p2 /mnt
    mkdir /mnt/boot
    mount /dev/nvme0n1p1 /mnt/boot
    archinstall..
------------------------------------------------------------------------------------------------------------------------------------------
                GUI 
| Chỉnh theme GTK                    | `lxappearance`                      |
| Chỉnh theme Qt (ứng dụng KDE/Qt)         `qt5ct`                             |
| Cấu hình màn hình (độ phân giải, vị trí) `arandr`                            |
| Chỉnh âm lượng PulseAudio                 `pavucontrol`                       |
| Cấu hình kết nối mạng                    `nm-connection-editor`, `nmtui`              |
| Chỉnh GNOME (theme, font, extension)      `gnome-tweaks`                      |
| Chỉnh cấu hình nâng cao GTK/GNOME        `dconf-editor`                      |
------------------------------------------------------------------------------------------------------------------------------------------
                Network

    iwctl
    station wlan0 scan on
    station wlan0 get-network
    station wlan0 connect wifi-name

or use nmtui
------------------------------------------------------------------------------------------------------------------------------------------
-Del file -> sudo ncdu / (with intuitive gui)
-Unistall -> 
  +del orphan: sudo pacman -Rns $(pacman -Qdtq)
  +del old cache: sudo paccache -r
  +Unistall installed software: ex: pacman -Q | grep -Ei 'i3|bspwm|xmonad|qtile|awesome|dwm|hyprland|sway'
                                ex: sudo pacman -Rns i3-wm bspwm awesome (-R: remove  -n: remove config files installed by package  -s: remove unused dependencies installed with the package)
------------------------------------------------------------------------------------------------------------------------------------------
✅ Cách an toàn để dọn dẹp /usr/lib
 1. Tìm thư viện không còn được dùng (orphans)
  
  sudo pacman -Qdt

→ Liệt kê các gói cài làm phụ thuộc, nhưng hiện không còn cần nữa.
 2. Xóa các gói orphan
  
  sudo pacman -Rns $(pacman -Qdtq)

Điều này sẽ:

    Gỡ các gói không cần nữa

    Gỡ luôn file trong /usr/lib của gói đó
