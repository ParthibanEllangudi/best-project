File system commands:

apt or apt-get -> ubuntu software
yum -> redhat

### sudo apt-get install vim

[sudo] password for sathya:
Reading package lists... Done
Building dependency tree
Reading state information... Done
vim is already the newest version (2:8.0.1453-1ubuntu1.4).
The following package was automatically installed and is no longer required:
  linux-hwe-5.4-headers-5.4.0-51
Use 'sudo apt autoremove' to remove it.
0 upgraded, 0 newly installed, 0 to remove and 2 not upgraded.
sathya@ubuntu:~$


### wget https://archive.apache.org/dist/hadoop/core/hadoop-2.6.5/hadoop-2.6.5.tar.gz


sathya@ubuntu:~/shell-test$ wget https://archive.apache.org/dist/hadoop/core/hadoop-2.6.5/hadoop-2.6.5.tar.gz
--2021-02-21 04:56:18--  https://archive.apache.org/dist/hadoop/core/hadoop-2.6.5/hadoop-2.6.5.tar.gz
Resolving archive.apache.org (archive.apache.org)... 138.201.131.134, 2a01:4f8:172:2ec5::2
Connecting to archive.apache.org (archive.apache.org)|138.201.131.134|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 199635269 (190M) [application/x-gzip]
Saving to: ‘hadoop-2.6.5.tar.gz’

hadoop-2.6.5.tar.gz        100%[=====================================>] 190.39M  8.70MB/s    in 23s

2021-02-21 04:56:41 (8.31 MB/s) - ‘hadoop-2.6.5.tar.gz’ saved [199635269/199635269]

### tar -xvf hadoop-2.6.5.tar.gz


sathya@ubuntu:~/shell-test$ du -hs
506M    .
sathya@ubuntu:~/shell-test$ du -hs hadoop-2.6.5
315M    hadoop-2.6.5
sathya@ubuntu:~/shell-test$ du -hs hadoop-2.6.5.tar.gz
191M    hadoop-2.6.5.tar.gz
sathya@ubuntu:~/shell-test$

sathya@ubuntu:~/shell-test$ mkdir -p test/test
sathya@ubuntu:~/shell-test$ ls test/
test
sathya@ubuntu:~/shell-test$ mkdir test1/test
mkdir: cannot create directory ‘test1/test’: No such file or directory
sathya@ubuntu:~/shell-test$

sathya@ubuntu:~/shell-test$ du -hs
703M    .
sathya@ubuntu:~/shell-test$ mkdir -p test/test
sathya@ubuntu:~/shell-test$ ls test/
test
sathya@ubuntu:~/shell-test$ mkdir test1/test
mkdir: cannot create directory ‘test1/test’: No such file or directory
sathya@ubuntu:~/shell-test$ ls
hadoop-2.6.5  hadoop-2.6.5.tar.gz  hadoop-2.6.5.zip  test
sathya@ubuntu:~/shell-test$ cp hadoop-2.6.5 test/
cp: -r not specified; omitting directory 'hadoop-2.6.5'
sathya@ubuntu:~/shell-test$ cp -r hadoop-2.6.5 test/
sathya@ubuntu:~/shell-test$

sathya@ubuntu:~/shell-test$ mv hadoop-2.6.5 test/test/
sathya@ubuntu:~/shell-test$ ls
hadoop-2.6.5.tar.gz  hadoop-2.6.5.zip  test
sathya@ubuntu:~/shell-test$ ls test/test/
hadoop-2.6.5
sathya@ubuntu:~/shell-test$

sathya@ubuntu:~/shell-test$ rm test/hadoop-2.6.5/
rm: cannot remove 'test/hadoop-2.6.5/': Is a directory
sathya@ubuntu:~/shell-test$ ls
hadoop-2.6.5.tar.gz  hadoop-2.6.5.zip  test
sathya@ubuntu:~/shell-test$ rm hadoop-2.6.5.zip
sathya@ubuntu:~/shell-test$ ls
hadoop-2.6.5.tar.gz  test
sathya@ubuntu:~/shell-test$ rm -rf test/hadoop-2.6.5/
sathya@ubuntu:~/shell-test$ ls test/
test
sathya@ubuntu:~/shell-test$


R W X
1 2 4

users group others
1+2+4 1+4   0

before:
drwxrwxr-x  3 sathya sathya      4096 Feb 21 05:08 /home/sathya/shell-test/
-rw-rw-r--  1 sathya sathya 199635269 Oct 11  2016  /home/sathya/shell-test/hadoop-2.6.5.tar.gz

directory -> chmod 750 /home/sathya/shell-test
drwxr-x---  3 sathya sathya      4096 Feb 21 05:08 /home/sathya/shell-test/
sathya@ubuntu:~$ ll /home/sathya/shell-test/hadoop-2.6.5.tar.gz
-rw-rw-r-- 1 sathya sathya 199635269 Oct 11  2016 /home/sathya/shell-test/hadoop-2.6.5.tar.gz

recursive -> chmod -R 750 /home/sathya/shell-test

sathya@ubuntu:~$ ll /home/sathya/shell-test/hadoop-2.6.5.tar.gz
-rwxr-x--- 1 sathya sathya 199635269 Oct 11  2016 /home/sathya/shell-test/hadoop-2.6.5.tar.gz*
sathya@ubuntu:~$
chown , chgrp


sathya@ubuntu:~$ netstat -tupln
(Not all processes could be identified, non-owned process info
 will not be shown, you would have to be root to see it all.)
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:38685         0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:37533           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:2049            0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:38699           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:43755           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:46861           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:111             0.0.0.0:*               LISTEN      -
tcp6       0      0 :::22                   :::*                    LISTEN      -
tcp6       0      0 ::1:631                 :::*                    LISTEN      -
tcp6       0      0 :::36475                :::*                    LISTEN      -
tcp6       0      0 :::38367                :::*                    LISTEN      -
tcp6       0      0 :::2049                 :::*                    LISTEN      -
tcp6       0      0 :::37953                :::*                    LISTEN      -
tcp6       0      0 :::38819                :::*                    LISTEN      -
tcp6       0      0 :::2181                 :::*                    LISTEN      -
tcp6       0      0 :::37961                :::*                    LISTEN      -
tcp6       0      0 :::111                  :::*                    LISTEN      -
tcp6       0      0 127.0.0.1:9200          :::*                    LISTEN      -
tcp6       0      0 ::1:9200                :::*                    LISTEN      -
tcp6       0      0 :::8080                 :::*                    LISTEN      -
tcp6       0      0 127.0.0.1:9300          :::*                    LISTEN      -
tcp6       0      0 ::1:9300                :::*                    LISTEN      -
udp        0      0 0.0.0.0:57318           0.0.0.0:*                           -
udp        0      0 127.0.0.53:53           0.0.0.0:*                           -
udp        0      0 0.0.0.0:68              0.0.0.0:*                           -
udp        0      0 0.0.0.0:111             0.0.0.0:*                           -
udp        0      0 0.0.0.0:631             0.0.0.0:*                           -
udp        0      0 0.0.0.0:966             0.0.0.0:*                           -
udp        0      0 0.0.0.0:42355           0.0.0.0:*                           -
udp        0      0 0.0.0.0:58947           0.0.0.0:*                           -
udp        0      0 0.0.0.0:2049            0.0.0.0:*                           -
udp        0      0 0.0.0.0:43872           0.0.0.0:*                           -
udp        0      0 0.0.0.0:60994           0.0.0.0:*                           -
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           -
udp6       0      0 :::49237                :::*                                -
udp6       0      0 :::111                  :::*                                -
udp6       0      0 :::966                  :::*                                -
udp6       0      0 :::50388                :::*                                -
udp6       0      0 :::2049                 :::*                                -
udp6       0      0 :::43158                :::*                                -
udp6       0      0 :::35909                :::*                                -
udp6       0      0 :::54173                :::*                                -
udp6       0      0 :::5353                 :::*                                -
sathya@ubuntu:~$ netstat -tupln | grep 2049
(Not all processes could be identified, non-owned process info
 will not be shown, you would have to be root to see it all.)
tcp        0      0 0.0.0.0:2049            0.0.0.0:*               LISTEN      -
tcp6       0      0 :::2049                 :::*                    LISTEN      -
udp        0      0 0.0.0.0:2049            0.0.0.0:*                           -
udp6       0      0 :::2049                 :::*                                -
sathya@ubuntu:~$ sudo netstat -tupln
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      793/systemd-resolve
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      1061/sshd
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      5050/cupsd
tcp        0      0 127.0.0.1:38685         0.0.0.0:*               LISTEN      1034/containerd
tcp        0      0 0.0.0.0:37533           0.0.0.0:*               LISTEN      -
tcp        0      0 0.0.0.0:2049            0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      1111/mysqld
tcp        0      0 0.0.0.0:38699           0.0.0.0:*               LISTEN      1036/rpc.mountd
tcp        0      0 0.0.0.0:43755           0.0.0.0:*               LISTEN      1036/rpc.mountd
tcp        0      0 0.0.0.0:46861           0.0.0.0:*               LISTEN      1036/rpc.mountd
tcp        0      0 0.0.0.0:111             0.0.0.0:*               LISTEN      790/rpcbind
tcp6       0      0 :::22                   :::*                    LISTEN      1061/sshd
tcp6       0      0 ::1:631                 :::*                    LISTEN      5050/cupsd
tcp6       0      0 :::36475                :::*                    LISTEN      1036/rpc.mountd
tcp6       0      0 :::38367                :::*                    LISTEN      1198/java
tcp6       0      0 :::2049                 :::*                    LISTEN      -
tcp6       0      0 :::37953                :::*                    LISTEN      1036/rpc.mountd
tcp6       0      0 :::38819                :::*                    LISTEN      -
tcp6       0      0 :::2181                 :::*                    LISTEN      1198/java
tcp6       0      0 :::37961                :::*                    LISTEN      1036/rpc.mountd
tcp6       0      0 :::111                  :::*                    LISTEN      790/rpcbind
tcp6       0      0 127.0.0.1:9200          :::*                    LISTEN      1247/java
tcp6       0      0 ::1:9200                :::*                    LISTEN      1247/java
tcp6       0      0 :::8080                 :::*                    LISTEN      1515/java
tcp6       0      0 127.0.0.1:9300          :::*                    LISTEN      1247/java
tcp6       0      0 ::1:9300                :::*                    LISTEN      1247/java
udp        0      0 0.0.0.0:57318           0.0.0.0:*                           1036/rpc.mountd
udp        0      0 127.0.0.53:53           0.0.0.0:*                           793/systemd-resolve
udp        0      0 0.0.0.0:68              0.0.0.0:*                           2677/dhclient
udp        0      0 0.0.0.0:111             0.0.0.0:*                           790/rpcbind
udp        0      0 0.0.0.0:631             0.0.0.0:*                           5052/cups-browsed
udp        0      0 0.0.0.0:966             0.0.0.0:*                           790/rpcbind
udp        0      0 0.0.0.0:42355           0.0.0.0:*                           1036/rpc.mountd
udp        0      0 0.0.0.0:58947           0.0.0.0:*                           -
udp        0      0 0.0.0.0:2049            0.0.0.0:*                           -
udp        0      0 0.0.0.0:43872           0.0.0.0:*                           821/avahi-daemon: r
udp        0      0 0.0.0.0:60994           0.0.0.0:*                           1036/rpc.mountd
udp        0      0 0.0.0.0:5353            0.0.0.0:*                           821/avahi-daemon: r
udp6       0      0 :::49237                :::*                                821/avahi-daemon: r
udp6       0      0 :::111                  :::*                                790/rpcbind
udp6       0      0 :::966                  :::*                                790/rpcbind
udp6       0      0 :::50388                :::*                                1036/rpc.mountd
udp6       0      0 :::2049                 :::*                                -
udp6       0      0 :::43158                :::*                                1036/rpc.mountd
udp6       0      0 :::35909                :::*                                -
udp6       0      0 :::54173                :::*                                1036/rpc.mountd
udp6       0      0 :::5353                 :::*                                821/avahi-daemon: r
sathya@ubuntu:~$ sudo netstat -tupln | grep 8080
tcp6       0      0 :::8080                 :::*                    LISTEN      1515/java
sathya@ubuntu:~$ sudo netstat -tupln | grep 9200
tcp6       0      0 127.0.0.1:9200          :::*                    LISTEN      1247/java
tcp6       0      0 ::1:9200                :::*                    LISTEN      1247/java
sathya@ubuntu:~$ sudo netstat -tupln | grep 3306
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      1111/mysqld
sathya@ubuntu:~$ sudo systemctl stop jenkins
sathya@ubuntu:~$ sudo netstat -tupln | grep 8080
sathya@ubuntu:~$ sudo systemctl status jenkins
● jenkins.service - LSB: Start Jenkins at boot time
   Loaded: loaded (/etc/init.d/jenkins; generated)
   Active: inactive (dead) since Sun 2021-02-21 05:29:38 CET; 1min 15s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 6110 ExecStop=/etc/init.d/jenkins stop (code=exited, status=0/SUCCESS)
  Process: 1253 ExecStart=/etc/init.d/jenkins start (code=exited, status=0/SUCCESS)

Feb 20 16:17:12 ubuntu su[1468]: + ??? root:jenkins
Feb 20 16:17:12 ubuntu su[1468]: pam_unix(su:session): session opened for user jenkins by (uid=0)
Feb 20 16:17:12 ubuntu su[1468]: pam_unix(su:session): session closed for user jenkins
Feb 20 16:17:13 ubuntu jenkins[1253]:    ...done.
Feb 20 16:17:13 ubuntu systemd[1]: Started LSB: Start Jenkins at boot time.
Feb 21 05:29:37 ubuntu systemd[1]: Stopping LSB: Start Jenkins at boot time...
Feb 21 05:29:37 ubuntu jenkins[6110]: Correct java version found
Feb 21 05:29:37 ubuntu jenkins[6110]:  * Stopping Jenkins Automation Server jenkins
Feb 21 05:29:38 ubuntu jenkins[6110]:    ...done.
Feb 21 05:29:38 ubuntu systemd[1]: Stopped LSB: Start Jenkins at boot time.
sathya@ubuntu:~$ date
Sun Feb 21 05:31:02 CET 2021
sathya@ubuntu:~$ sudo systemctl start jenkins
sathya@ubuntu:~$ sudo systemctl status jenkins
● jenkins.service - LSB: Start Jenkins at boot time
   Loaded: loaded (/etc/init.d/jenkins; generated)
   Active: active (exited) since Sun 2021-02-21 05:31:49 CET; 2s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 6110 ExecStop=/etc/init.d/jenkins stop (code=exited, status=0/SUCCESS)
  Process: 6198 ExecStart=/etc/init.d/jenkins start (code=exited, status=0/SUCCESS)

Feb 21 05:31:47 ubuntu systemd[1]: Starting LSB: Start Jenkins at boot time...
Feb 21 05:31:48 ubuntu jenkins[6198]: Correct java version found
Feb 21 05:31:48 ubuntu jenkins[6198]:  * Starting Jenkins Automation Server jenkins
Feb 21 05:31:48 ubuntu su[6258]: Successful su for jenkins by root
Feb 21 05:31:48 ubuntu su[6258]: + ??? root:jenkins
Feb 21 05:31:48 ubuntu su[6258]: pam_unix(su:session): session opened for user jenkins by (uid=0)
Feb 21 05:31:48 ubuntu su[6258]: pam_unix(su:session): session closed for user jenkins
Feb 21 05:31:49 ubuntu jenkins[6198]:    ...done.
Feb 21 05:31:49 ubuntu systemd[1]: Started LSB: Start Jenkins at boot time.
sathya@ubuntu:~$ date
Sun Feb 21 05:31:59 CET 2021
sathya@ubuntu:~$

sathya@ubuntu:~$ grep -rnw /home/sathya/logs/ -e "SUCCESS"
/home/sathya/logs/spark-maven-shade-build.log:672:[INFO] BUILD SUCCESS
sathya@ubuntu:~$



REGEX:

^
$
sathya@ubuntu:~$ ping www.google.com
PING www.google.com (142.250.71.4) 56(84) bytes of data.
64 bytes from maa03s34-in-f4.1e100.net (142.250.71.4): icmp_seq=1 ttl=128 time=9.54 ms
64 bytes from maa03s34-in-f4.1e100.net (142.250.71.4): icmp_seq=2 ttl=128 time=8.27 ms
64 bytes from maa03s34-in-f4.1e100.net (142.250.71.4): icmp_seq=3 ttl=128 time=9.49 ms
64 bytes from maa03s34-in-f4.1e100.net (142.250.71.4): icmp_seq=4 ttl=128 time=7.52 ms
64 bytes from maa03s34-in-f4.1e100.net (142.250.71.4): icmp_seq=5 ttl=128 time=27.3 ms
^C
--- www.google.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4008ms
rtt min/avg/max/mdev = 7.522/12.434/27.346/7.495 ms
sathya@ubuntu:~$ ping www.google1.com
ping: www.google1.com: Name or service not known
sathya@ubuntu:~$ ping 192.168.59.17
PING 192.168.59.17 (192.168.59.17) 56(84) bytes of data.
^C
--- 192.168.59.17 ping statistics ---
33 packets transmitted, 0 received, 100% packet loss, time 32745ms

sathya@ubuntu:~$

sathya@ubuntu:~$ ping 192.168.93.159
PING 192.168.93.159 (192.168.93.159) 56(84) bytes of data.
64 bytes from 192.168.93.159: icmp_seq=1 ttl=64 time=0.106 ms
64 bytes from 192.168.93.159: icmp_seq=2 ttl=64 time=0.116 ms
64 bytes from 192.168.93.159: icmp_seq=3 ttl=64 time=0.246 ms
64 bytes from 192.168.93.159: icmp_seq=4 ttl=64 time=0.117 ms
64 bytes from 192.168.93.159: icmp_seq=5 ttl=64 time=0.193 ms
64 bytes from 192.168.93.159: icmp_seq=6 ttl=64 time=0.121 ms
64 bytes from 192.168.93.159: icmp_seq=7 ttl=64 time=0.120 ms
64 bytes from 192.168.93.159: icmp_seq=8 ttl=64 time=0.126 ms
64 bytes from 192.168.93.159: icmp_seq=9 ttl=64 time=0.116 ms
64 bytes from 192.168.93.159: icmp_seq=10 ttl=64 time=0.172 ms
64 bytes from 192.168.93.159: icmp_seq=11 ttl=64 time=0.165 ms
64 bytes from 192.168.93.159: icmp_seq=12 ttl=64 time=0.120 ms
64 bytes from 192.168.93.159: icmp_seq=13 ttl=64 time=0.118 ms
64 bytes from 192.168.93.159: icmp_seq=14 ttl=64 time=0.114 ms
64 bytes from 192.168.93.159: icmp_seq=15 ttl=64 time=0.195 ms
64 bytes from 192.168.93.159: icmp_seq=16 ttl=64 time=0.118 ms
64 bytes from 192.168.93.159: icmp_seq=17 ttl=64 time=0.123 ms
64 bytes from 192.168.93.159: icmp_seq=18 ttl=64 time=0.120 ms
64 bytes from 192.168.93.159: icmp_seq=19 ttl=64 time=0.121 ms
64 bytes from 192.168.93.159: icmp_seq=20 ttl=64 time=0.211 ms
^C
--- 192.168.93.159 ping statistics ---
20 packets transmitted, 20 received, 0% packet loss, time 19444ms
rtt min/avg/max/mdev = 0.106/0.141/0.246/0.042 ms
sathya@ubuntu:~$

sathya@ubuntu:~$ telnet 127.0.0.1 8080
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
Connection closed by foreign host.
sathya@ubuntu:~$ telnet 127.0.0.1 9200
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
^C^[[A^C^C
Connection closed by foreign host.
sathya@ubuntu:~$ telnet 127.0.0.1 3306
Trying 127.0.0.1...
Connected to 127.0.0.1.
Escape character is '^]'.
[
5.7.33-0ubuntu0.18.04.16-.S^]9qS1_7xm=mysql_native_password^CConnection closed by foreign host.
sathya@ubuntu:~$ telnet www.google.com 8080
Trying 142.250.71.4...
^C
sathya@ubuntu:~$


# File Operations

sathya@ubuntu:~/besant-devops/file$ cat text.txt | cut -f2 -d","
2
b

sathya@ubuntu:~/besant-devops/file$ cat text.txt | cut -f3 -d","
3
c

sathya@ubuntu:~/besant-devops/file$ cat text.txt | cut -f4 -d","
4
d

sathya@ubuntu:~/besant-devops/file$ cat text.txt 
1,2,3,4,5,6
a,b,c,d,e,f

sed -i 's/1/11/g' text.txt > text1.txt
 2091  sed -i 's/a/aa/g' text1.txt > text2.txt
 2092  cat text2.txt
 2093  cat text.txt
 2094  sed -i 's/a/aa/g' text.txt
 2095  cat text.txt
 2096  sed -i 's/2/22/g' text.txt
 2097  sed -i 's/b/bb/g' text1.txt
 2098  cat text.txt
 2099  sed -i 's/b/bb/g' text.txt

