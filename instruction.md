                Archlinux installation
    connect network use iwctl
    mkfs.fat -F32 /dev/nvme0n1p1
    mkfs.ext4 /dev/nvme0n1p2
    mount /dev/nvme0n1p2 /mnt
    mkdir /mnt/boot
    mount /dev/nvme0n1p1 /mnt/boot
    archinstall..

                GUI 
| Chỉnh theme GTK                    | `lxappearance`                      |
| Chỉnh theme Qt (ứng dụng KDE/Qt)         `qt5ct`                             |
| Cấu hình màn hình (độ phân giải, vị trí) `arandr`                            |
| Chỉnh âm lượng PulseAudio                 `pavucontrol`                       |
| Cấu hình kết nối mạng                    `nm-connection-editor`, `nmtui`              |
| Chỉnh GNOME (theme, font, extension)      `gnome-tweaks`                      |
| Chỉnh cấu hình nâng cao GTK/GNOME        `dconf-editor`                      |

                Network

    iwctl
    station wlan0 scan on
    station wlan0 get-network
    station wlan0 connect wifi-name

or use nmtui

