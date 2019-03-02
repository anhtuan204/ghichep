# Reset password Linux KVM qcow2 image/vm bằng 

Bước 1 ; Cài đặt:

```sh
sudo yum install libguestfs-tools

#Fedora Linux user run dnf command:
sudo dnf install libguestfs-tools

#Debian/Ubuntu Linux user run apt command/apt-get command:
sudo apt install libguestfs-tools
```

Bước 2: Thực hiện reset:

- Tăt máy ảo:

`
virsh list
virsh shutdown test71
`

- Kiểm tra vị trí file img:

`
virsh dumpxml test71 | grep 'source file'
`

Ví dụ:       
`<source file='/var/lib/libvirt/images/testvlan71.img'/>`

- Tạo pass mới:
```sh
[root@nhmonlog01 ~]# openssl passwd -1 nhanhoa2019#@!
$1$13clnCwI$PxFDBb.IEVVsyFRhIdO2y.
```

- Sử dụng guestfish để sửa file img:

```sh
guestfish --rw -a /var/lib/libvirt/images/testvlan71.img
```

`launch` or `run` để chạy backend

`list-filesystems` list các phân vùng

`mount` mount disk 

`vi /etc/shadow` edit file password để lưu lại password cũ hoặc thay thế bằng password đã hash ở trên
(ví dụ: `root:$1$2FusLVIf$UiQyH5pLQ2c59bFeWyq2j0::0:99999:7:::` )

```sh
><fs> run
><fs> list-filesystems
/dev/sda1: ext4
/dev/sda3: swap
/dev/VolGroup00/LogVol01: xfs
><fs> mount /dev/VolGroup00/LogVol01 /
><fs> vi /etc/shadow
```

Thay thế bằng password mới và `exit` 

Bước 3: Thực hiện start máy ảo và kiểm tra lại:
`
 virsh start test71
`

# Virt-customize
A note about virt-customize command
If you find above method difficult try the following simple command:
```sh
virsh shutdown test71
virt-customize -a /var/lib/libvirt/images/testvlan71.img --root-password password:Nhanhoa2019@@ --uninstall cloud-init
```