# Big sur、windows10、archlinux三系统配置Bluetooth

> 我在`TkinkPad X1`上同时安装了`windows`、`Archlinux`和`Big Sur`，三个系统可共用蓝牙耳机。首先在三个系统分别连接蓝牙耳机，其次在 `Big Sur`中导出连接消息，查看连接密码。再次修改`windows`和`Archlinux`连接密码。注意`windows`和`Archlinux`连接密码`Big Sur`连接密码从后向前每两位为一组颠倒，同时`Archlinux`的连接密码字母需大写。
- 蓝牙耳机分别配对`windows`、`archlinx`和`windows`
- `MAC`中首先导出蓝牙配对密钥
* 下载`hacktool`;
*  使用`hacktool`-`工具`-`蓝牙`导出蓝牙配对信息，找到配对密钥。
- 修改`winodows`中蓝牙配对密钥
* 以管理员权限打开cmd；
* 使用管理员权限运行`regedit`。运行`psexec -si regedit`;
打开`ControlSet001\Services\BTHPORT\Parameters\你的蓝牙mac地址`下蓝牙密钥与`mac\下一致，注意字母要大写。
- 修改`linux`中蓝牙配对密钥
* 使用`su`进入超级用户。
* 进入`cd /var/lib/bluetooth/你的蓝牙mac地址`，
* 编辑`vim info`。
修改`LinkKey`下`key`与mac中一致，密钥大写，顺序不要改。 

参考[Archlinux Wiki](https://wiki.archlinux.org/index.php/Bluetooth)

