# 🇺🇲 hid_sony fixed for fake DualShock 4 gamepads

Some fake DualShock 4 fail while getting feature report 0x81. This driver is patched to get feature report 0x12 as a fallback.

`sony 0003:054C:09CC.001F: failed to retrieve feature report 0x81 with the DualShock 4 MAC address`

Another problem is: sometimes the variable `calib->sens_denom` returns zero, and the kernel hangs up. In this driver `calib->sens_denom` never returns zero.

# Installing

Install DKMS first.

```
sudo git clone https://github.com/ozz-is-here/hid-sony-fix-dkms.git /usr/src/hid-sony-fix-dkms-0.1
sudo dkms install -m hid-sony-fix-dkms -v 0.1
```

Add `blacklist hid_sony` to `/etc/modprobe.d/blacklist.conf`.

# Uninstalling

```
sudo dkms remove -m hid-sony-fix-dkms -v 0.1
sudo rm -rf /usr/src/hid-sony-fix-dkms-0.1
```

# 🇷🇺 Исправленный hid_sony для поддельных геймпадов DualShock 4

Некоторые поддельные DualShock 4 не могут получить feature report 0x81. Данный драйвер пропатчен так, чтобы получать feature report 0x12 как резервный вариант.

`sony 0003:054C:09CC.001F: failed to retrieve feature report 0x81 with the DualShock 4 MAC address`

Другая проблема: иногда переменная `calib->sens_denom` возвращает ноль, и ядро зависает. В этом драйвере `calib->sens_denom` никогда не возвращает ноль.

# Установка

Сначала установите DKMS.

```
sudo git clone https://github.com/ozz-is-here/hid-sony-fix-dkms.git /usr/src/hid-sony-fix-dkms-0.1
sudo dkms install -m hid-sony-fix-dkms -v 0.1
```

Добавьте `blacklist hid_sony` в `/etc/modprobe.d/blacklist.conf`.

# Удаление

```
sudo dkms remove -m hid-sony-fix-dkms -v 0.1
sudo rm -rf /usr/src/hid-sony-fix-dkms-0.1
```