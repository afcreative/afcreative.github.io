---
title: Cara otentikasi SSH untuk remote server pada linux atau windows
date: 2021-11-28 13:22:55 +0700
categories: [Deployment]
tags: [command line interface, bash, shell, ssh, remote server, linux, windows]
---
## Pengertian
Secure shell atau SSH adalah protokol transfer yang memungkinkan penggunanya untuk mengontrol sebuah perangkat secara remote atau dari jarak jauh melalui koneksi internet. Dengan SSH, Anda bisa mengakses dan memodifikasi berbagai macam pengaturan maupun file yang ada di dalam server tersebut. Fungsi SSH adalah sebagai media transfer data aman dan terpercaya yang bisa digunakan secara remote atau dari jarak jauh.

## Shell
```bash
$ ssh
```
Respon:
```bash
usage: ssh [-1246AaCfGgKkMNnqsTtVvXxYy] [-b bind_address] [-c cipher_spec]
[-D [bind_address:]port] [-E log_file] [-e escape_char] [-F configfile]
[-I pkcs11] [-i identity_file] [-J [user@]host[:port]] [-L address]
[-l login_name] [-m mac_spec] [-O ctl_cmd] [-o option] [-p port]
[-Q query_option] [-R address] [-S ctl_path] [-W host:port]
[-w local_tun[:remote_tun]] [user@]hostname [command]
```

Fungsi argumen lengkap terkait SSH:

[SSH Cheat Sheet](https://lzone.de/cheat-sheet/SSH)

## Format Penulisan
Berikut ini penggunaan dasar dari SSH yang umumnya digunakan:
> $ ssh **nama_pengguna**@**host_server** -p **nomor_port**

Keterangan:

| Argumen | Penjelasan |
| ----------- | ----------- |
| **nama_pengguna** | Nama pengguna yang terdaftar dan memiliki akses (bash) server. |
| **host_server** | IP address atau domain website server. |
| **nomor_port** | Nomor port server. |


## Contoh Penulisan
- Tanpa *port* yang ditentukan atau spesifik:
```bash
$ ssh user@192.168.0.1
```

- Dengan *port* yang ditentukan atau spesifik:
```bash
$ ssh admin@127.0.0.1 -p 21
```

- Dengan alamat domain situs atau server:
```bash
$ ssh root@afcreative.github.io -p 8083
```

## Penggunaan
Melakukan otentikasi ke remote server:
```bash
$ ssh admin@127.0.0.1 -p 21
```

Respon sukses jika pengguna pertama kali akses server melalui SSH ke server yang sudah terpasang module SSH:
```shell
The authenticity of host '127.0.0.1 (127.0.0.1)' can't be established.
ECDSA key fingerprint is SHA256:RrUx1LEYT+M0zVGd1a3DUBsDQ2a/U57smlfF1xHrOeps7j3uC8.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Konfirmasi intruksi untuk akses:
```bash
yes
```

Masukkan kata sandi pengguna, penulisan kata sandi tidak akan terlihat maka lakukan dengan baik. Jika dirasa salah lebih baik batalkan dengan perintah <kbd>CTRL</kbd>+<kbd>C</kbd>, tekan <kbd>Enter</kbd> untuk memproses otentikasi SSH:
```bash
admin@127.0.0.1's password:
```

Respon jika berhasil proses otentikasi SSH dengan nama pengguna dan kata sandi yang benar:
```bash
Linux Debian 4.9.272-2 (2021-07-19) x86_64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun May 23 16:50:11 2021 from 114.124.172.253
admin@afcreative:~#
```
Jika sudah melakukan operasi pada server maka cukup menutup terminal atau cmd, maka remote akan berhenti secara otomatis. Namun jika ingin keluar pengguna SSH dari remote server dengan teratur bisa lakukan ini:
```bash
admin@afcreative:~# exit
```

## Alat Yang Digunakan Dalam Penggunaan
- [Windows PowerShell](https://docs.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.2)<br/>Sebagai command-line shell.
- [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701)<br/>Sebagai command-line tool.
