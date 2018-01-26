# Nagios Solaris Checks

## CPU

**Perf data on/off:** On

**Nagios Server Command line:**

[nagios@SomeServer ~]$ /usr/local/nagios/libexec/check\_by\_ssh -q -H 192.168.100.69 -C &quot;/home/supergoodmike/bin/nagios/check\_solaris\_cpu.sh&quot; -l supergoodmike

CPU OK : user=12% system=3% iowait=0% idle=85% | cpu\_user=12%;70;90; cpu\_sys=3%;70;90; cpu\_iowait=0%;70;90; cpu\_idle=85%;

**Host Command line:**

/home/supergoodmike/bin/nagios/check\_solaris\_cpu.sh

**Usage:**

./check\_solaris\_cpu.sh -w &lt;warn&gt; -c &lt;crit&gt; where thresholds are measured in percent

-uw &lt;user\_cpu warn&gt; -uc &lt;user\_cpu crit&gt;

-sw &lt;sys\_cpu warn&gt; -sc &lt;sys\_cpu crit&gt;

-iw &lt;io\_wait\_cpu warn&gt; -ic &lt;io\_wait\_cpu crit&gt;

-i &lt;intervals in second&gt;   -n &lt;report number&gt;

## Disk

**Perf data on/off:** On

**Nagios Server Command line:**

[nagios@SomeServer ~]$ /usr/local/nagios/libexec/check\_by\_ssh -q -H 192.168.100.69 -C &quot;/home/supergoodmike/bin/nagios/check\_solaris\_disk.sh -w 85 -c 95 -p /&quot; -l supergoodmike

OK: current disk usage is 31% Available Space 13G| disk\_used=31%;85;95;

**Host Command line:**

/home/supergoodmike/bin/nagios/check\_solaris\_disk.sh -w 85 -c 95 -p /

**Usage:**

./check\_solaris\_disk.sh: -w warn\_threshold -c crit\_threshold -p mount\_point where thresholds are measured in percent

## String in log

**Perf data on/off:** off

**Nagios Server Command line:**

[nagios@SomeServer ~]$ /usr/local/nagios/libexec/check\_by\_ssh -q -H 192.168.100.69 -C &quot;/home/supergoodmike/bin/nagios/check\_solaris\_log.sh -l /var/adm/messages -s nfs -t 300&quot; -l supergoodmike -t 20

OK: Nothing found

**Host Command line:**

/home/supergoodmike/bin/nagios/check\_solaris\_log.sh -l /var/adm/messages -s nfs -t 300

**Usage:**

./check\_solaris\_log.sh: -l &lt;logfile &gt;-s &lt;string&gt; -t &lt;secs back&gt;

## Swap Usage

**Perf data on/off:** On

**Nagios Server Command line:**

[nagios@SomeServer ~]$ /usr/local/nagios/libexec/check\_by\_ssh -q -H 192.168.100.69 -C &quot;/home/supergoodmike/bin/nagios/check\_solaris\_swap.sh -w 85 -c 95&quot; -l supergoodmike

OK: Swap utilization is at 7.700 %| swap\_used=7.700;85;95;

**Host Command line:**

/home/supergoodmike/bin/nagios/check\_solaris\_swap.sh -w 85 -c 95

**Usage:**

./check\_solaris\_swap.sh [-w &lt;warn&gt;] [-c &lt;crit&gt;] where thresholds are measured in percent

## Memory Usage

**Perf data on/off:** On

**Nagios Server Command line:**

[nagios@SomeServer ~]$ /usr/local/nagios/libexec/check\_by\_ssh -q -H 192.168.100.69 -C &quot;/home/supergoodmike/bin/nagios/check\_mem.pl -u -C -w 85 -c 95&quot; -l supergoodmike

OK - 35.5% (5851548 kB) used.|TOTAL=16463327KB;;;; USED=5851548KB;13993827;15640160;; FREE=10611779KB;;;; CACHES=7041011KB;;;;

**Host Command line:**

/home/supergoodmike//bin/nagios/check\_mem.pl -u -C -w 85 -c 95

**Usage:**

 check\_mem.pl -&lt;f|u&gt; -w &lt;warnlevel&gt; -c &lt;critlevel&gt;

options:

 -f           Check FREE memory

 -u           Check USED memory

 -C           Count OS caches as FREE memory

 -w PERCENT   Percent free/used when to warn

 -c PERCENT   Percent free/used when critical
