# GPGME  errors on archlinux


问题：
```
sudo pacman -Syyu
error: GPGME error: 无数据
error: GPGME error: 无数据
error: GPGME error: 无数据
```
Delete:

```
sudo rm /var/lib/pacman/sync/*db.sig*
```

Then:

```
sudo pacman-key --init

sudo pacman-key --populate archlinux

sudo pacman -Syy

sudo pacman -Syyu
```

Done!

