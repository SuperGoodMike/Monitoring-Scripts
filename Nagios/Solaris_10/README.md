
CPU
Perf data : Yes
Nagios Server Command line:
[nagios@Someserver ~]$ /usr/local/nagios/libexec/check_by_ssh -q -H 192.168.1.69-C "/home/supergoodmike/bin/nagios/check_solaris_cpu.sh" -l supergoodmike 
CPU OK : user=12% system=3% iowait=0% idle=85% | cpu_user=12%;70;90; cpu_sys=3%;70;90; cpu_iowait=0%;70;90; cpu_idle=85%;
Host Command line:
/home/supergoodmike/bin/nagios/check_solaris_cpu.sh
Usage: 
./check_solaris_cpu.sh [-w <warn>] [-c <crit>] where thresholds are measured in percent
                                [-uw <user_cpu warn>] [-uc <user_cpu crit>]
                                [-sw <sys_cpu warn>] [-sc <sys_cpu crit>]
                                [-iw <io_wait_cpu warn>] [-ic <io_wait_cpu crit>]
                                [-i <intervals in second>] [-n <report number>]

Disk
Perf data : Yes
Nagios Server Command line:
[nagios@Someserver ~]$ /usr/local/nagios/libexec/check_by_ssh -q -H 192.168.1.69-C "/home/supergoodmike/bin/nagios/check_solaris_disk.sh -w 85 -c 95 -p /" -l supergoodmike 
OK: current disk usage is 31% Available Space 13G| disk_used=31%;85;95;
Host Command line:
/home/supergoodmike/bin/nagios/check_solaris_disk.sh -w 85 -c 95 -p /
Usage: 
./check_solaris_disk.sh: -w warn_threshold -c crit_threshold -p mount_point where thresholds are measured in percent


String in log 
Perf data : No
Nagios Server Command line:
[nagios@Someserver ~]$ /usr/local/nagios/libexec/check_by_ssh -q -H 192.168.1.69-C "/home/supergoodmike/bin/nagios/check_solaris_log.sh -l /var/adm/messages -s nfs -t 300" -l supergoodmike -t 20
OK: Nothing found
Host Command line:
/home/supergoodmike/bin/nagios/check_solaris_log.sh -l /var/adm/messages -s nfs -t 300
Usage: 
./check_solaris_log.sh: -l <logfile >-s <string> -t <secs back>

Swap Usage
Perf data : Yes
Nagios Server Command line:
[nagios@Someserver ~]$ /usr/local/nagios/libexec/check_by_ssh -q -H 192.168.1.69-C "/home/supergoodmike/bin/nagios/check_solaris_swap.sh -w 85 -c 95" -l supergoodmike 
OK: Swap utilization is at 7.700 %| swap_used=7.700;85;95;
Host Command line:
/home/supergoodmike/bin/nagios/check_solaris_swap.sh -w 85 -c 95
Usage: 
./check_solaris_swap.sh [-w <warn>] [-c <crit>] where thresholds are measured in percent

Memory Usage
Perf data : Yes
Nagios Server Command line:
[nagios@Someserver ~]$ /usr/local/nagios/libexec/check_by_ssh -q -H 192.168.1.69-C "/home/supergoodmike/bin/nagios/check_mem.pl -u -C -w 85 -c 95" -l supergoodmike 
OK - 35.5% (5851548 kB) used.|TOTAL=16463327KB;;;; USED=5851548KB;13993827;15640160;; FREE=10611779KB;;;; CACHES=7041011KB;;;;
Host Command line:
/home/supergoodmike/bin/nagios/check_mem.pl -u -C -w 85 -c 95
Usage: 
 check_mem.pl -<f|u> -w <warnlevel> -c <critlevel>

options:
 -f           Check FREE memory
 -u           Check USED memory
 -C           Count OS caches as FREE memory
 -w PERCENT   Percent free/used when to warn
 -c PERCENT   Percent free/used when critical
