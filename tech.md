CLARK'S MISCELLANY: TECHNICAL EDITION
=====================================

HTTP CODES
----------
- 200 OK
- 201 Created
- 202 Accepted
- 204 No content
- 206 Partial Content
- 301 Redirect (perm)
- 302 Redirect (temp)
- 303 Redirect (see other)
- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 410 Gone
- 416 Requested Range Not Satisfiable
- 500 Internal Server Error
- 501 Method not allowed
- 502 Bad Gateway
- 503 Service Unavailable
- 504 Gateway timeout

OSI LAYER MODEL
---------------
- 7 Application
- 6 Presentation
- 5 Session
- 4 Transmission
- 3 Network
- 2 Data
- 1 Physical

ICMP 
----
- 0 Echo Reply
- 3 Dest unreachable
- 8 Echo request
- 11 TTL expired

COMMON PORTS
------------
- 21 FTP
- 22 SSH
- 23 Telnet
- 25 SMTP
- 53 DNS
- 80 HTTP
- 110 POP3
- 123 NTP
- 137 SMB (NetBIOS over TCP/IP)
- 139 SMB (NetBIOS over TCP/IP)
- 143 IMAP
- 161 SNMP
- 443 HTTPS
- 445 CIFS
- 1080 SOCKS5
- 1433 MSSQL
- 3306 MySQL
- 3389 RDP
- 5666 Jabber/XMPP
- 5672 AMQP
- 6379 redis
- 6667 IRC
- 61613 ActiveMQ Stomp
- 61616 ActiveMQ Openwire

TCP THREE WAY HANDSHAKE
-----------------------
- SYN
- SYN ACK
- ACK

COMMON RFCS
-----------
- 791  IP
- 792  ICMP
- 793  TCP
- 951  Hostnames
- 1157 SNMP
- 1191 PMTUD
- 1918 Reserved IP spaces
- 2119 Keywords in RFCs (SHOULD/MUST/MAY, etc)
- 2131 DHCP
- 2317 Classless in-addr.arpa delegation
- 2324 Hypertext Coffee Pot Control Protocol
- 2606 Reserved TLDs (for testing, docs, etc)
- 2616 HTTP/1.1
- 2822 Email format
- 3513 IPV6 address format
- 3927 Linklocal
- 5321 SMTP

SMTP
----
```
220 remote.host.name ready
HELO my.host.name
250 Hello my.host.name!
MAIL FROM:<foo@bar.baz>
250 OK
RCPT TO:<tom@woot.co.uk>
250 OK
DATA
354 End with <CR><LF>.<CR><LF>
Foo
Bar
Baz
.
250: Queued as xxxx
QUIT
221 Bye!
```

POP3
----
```
USER foo
xxx Hello foo
PASS xxxx
xxx User foo logged in
LIST / STAT
xxx
RETR 1
xxx
DELE 1
xxx
BYE
```

FTP MODES
---------
### Active
```
command : client >1023 -> server 21
data    : client >1023 <- server 20
```

### Passive
```
command : client >1023 -> server 21
data    : client >1023 -> server >1023
```

TOOLKIT
-------
- Cron locking: http://unixwiz.net/tools/lockrun.html
- MySQL hackery: http://www.maatkit.org/
- sysdig: http://www.sysdig.org/
- perf: https://perf.wiki.kernel.org/index.php/Main_Page
- procinfo - summary of system information from /proc
- pidstat  - per-process(id) stats, inc. CPU% usage

### Realtime MySQL stats
Needs Maatkit

```
$ tcpdump port 3306 -s 65535 -x -n -q -tttt | mk-query-digest --type=tcpdump --print --noreport
```


### rot13
```
$ echo foo | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```

### Discover proxy (on MS networks)
```
$ curl http://wpad/wpad.dat
```

### Find ldap server (on MS networks)
```
$ host -t srv _ldap._tcp
```


VIM
---
```
ga - ascii value for current character
gU <dir> - uppercase <dir>
:w !sudo tee % - save file as root
:r!<cmd> - insert output of <cmd> at current location

g- : move backwards in time (undo)
g+ : move forwards in time (redo)

:ls - list open files
:bN - switch to file N
:bn / :bp - next / prev file

do / dp - merge in/out with vimdiff

zc / zo - close/open fold

Replace x with newline: (\r = CR, \n == nul in replacement)
s/x/\r/
```

REDHAT/CENTOS
-------------
### When was this machine built?
```
$ date -d @$(rpm -q --qf '%{INSTALLTIME}' basesystem)
```

RPM
---
### List installed RPMs
```
$ rpm -qa
```

### List installed RPMs, with architecture
```
$ rpm -qa --qf "%{n}-%{arch}\n"
```

### Info on <package> (inc installation date)
```
$ rpm -qi <package> 
```

### Which RPM installed <file>
```
$ rpm -qf <file>
```

### List all files in <file.rpm>
```
$ rpm -qlp <file>
```

### List all files installed with <package>
```
$ rpm -ql <package> 
```

DEB
---
### List installed debs
```
$ dpkg -l
```

### List included files in <pkg> (if installed)
```
$ dpkg -L <pkg>
```

### List files in <pkg> (file)
```
$ dpkg --contents <pkg>
```

### Report which package owns <file>
```
$ dpkg -S /path/to/<file>
```

### Reinstall <package>
```
$ apt-get install --reinstall <package>
```

### Preconfigure package
```
$ debconf-get-selections | grep package_name > package_name.conf
$ cat package_name.conf | debconf-set-selections
```

Mirror size: http://www.debian.org/mirror/size

DEBIAN
------
### Prevent packages from starting daemons
```
$ echo "exit 101" > /usr/sbin/policy-rc.d
```

PUPPET
------
### Test a class
```
$ puppet apply --modulepath=/etc/puppet/modules -e 'include <module>' --debug
```

### Force run
```
$ puppet agent --test`
```

UBUNTU REPOS
------------
### Main
Officially supported software.

### Restricted
Supported software that is not available under a completely free license.

### Universe
Community maintained software, i.e. not officially supported software.

### Multiverse
Software that is not free. 

OPENSSL
-------
### Self-signed certificate
```
$ openssl req -new -newkey rsa:1024 -nodes -keyout host.key > host.csr
$ openssl x509 -days 3650 -signkey host.key -req < host.csr > host.crt
```

### View cert
```
$ openssl x509 -noout -text -in <cert>
```

### View DER certificate
```
$ openssl x509 -noout -text -inform der -in <cert>
```

### Test remote ssl
```
$ openssl s_client -showcerts -connect host:port
```

### Generate MD5 hash (for passwd, etc)
```
$ openssl passwd -1
```

PENETRATION TESTERS
-------------------
- NCC
- Sec-1
- Ioactive
- Comsec

MANPAGES
--------
```
1 User commands          Executable commands or scripts.
2 System calls           Functions provided by the kernel.
3 Library calls          Functions within system libraries.
4 Special files          Usually found in /dev
5 File formats           E.g. /etc/passwd's format
6 Games                  Or other frivolous programs
7 Macro packages         Such as man macros.
8 System administration  Programs typically only run by root.
9 Kernel routines        Non-standard calls and internals.
```

CRYPT PREFIXES
--------------
- $1$ MD5
- $2$ bcrypt
- $6$ SHA

MEGACLI
-------
### List physical devices
```
$ MegaCli -PDList -aALL
```

### List logical devices
```
$ MegaCli -LDInfo -Lall -aALL
```

### Create LD
```
$ MegaCli -CfgLdAdd -rRAID-LEVEL [ENCLOSURE:SLOT,ENCLOSURE:SLOT] -aADAPTOR
```

### Delete LD
```
$ MegaCli -CfgLdDel -LLD# -aADAPTOR
```

ISO
---
- 216  - Paper sizes
- 639  - Language codes
- 3166 - Country codes
- 8601 - Time formats

KILL SIGNALS
------------
- 1  SIGHUP
- 2  SIGINT
- 3  SIGQUIT
- 9  SIGKILL
- 15 SIGTERM
- 17 SIGSTOP
- 19 SIGCONT

MAGIC SYSRQ
-----------
- r - Switch keyboard from raw mode
- e - Send SIGTERM to all processes (bar init)
- i - Send SIGKILL to all processes (bar init)
- s - Sync all mounted filesystems
- u - Remount all filesystems in read-only mode
- b - Reboot
- h - help

ETHERNET CABLES - 568A (568B)
-----------------------------
```
1 Green/White  (Orange/White)
2 Green        (Orange)
3 Orange/White (Green/White)
4 Blue
5 Blue/White
6 Orange       (Green)
7 Brown/White
8 Brown
```

(crossover = 568A->568B)

802 STANDARDS
-------------
- 802.1af  - Power Over Ethernet
- 802.1q   - VLAN tagging
- 802.1x   - Port-based access security
- 802.11a  - 5Ghz
- 802.11ac - 5Ghz
- 802.11b  - 2.4GHz 11mbit
- 802.11g  - 2.4GHz 54mbit
- 802.11n  - 2.4GHz + 5GHz 108mbit
- 802.11x  - port-based network authentication

GRUB
----
### Reboot to a specific entry next time - once
```
$ echo "savedefault --default=2 --once" | grub --batch
```

DISK BENCHMARKS
---------------
- bonnie++
- iozone

MD5
---
- MD5Sum of zero bytes: d41d8cd98f00b204e9800998ecf8427e

UPTIME  
------
```
          Day     Month   Year
90      - 2h 24m   3d 1h    36d 12h
95      - 1h 12m   1d 13h   18d 6h
99      - 14m 24s  7h 18m   3d 16h
99.5    - 7m 12s   3h 36m   1d 20h
99.9    - 1m 26s   43m 50s  8h 46m  (three nines)
99.95   - 43s      21m 55s  4h 23m  (three and a half nines)
99.99   - 8.6s     4m 23s   52m 36s (four nines)
99.999  - 0.9s     26s      5m 16s  (five nines)
99.9999 - 0.1s     2.6s     32s     (six nines)
```

IOS
---
### Which MACs on which ports
```
> show mac-address-table
```

ASCII
-----
```
---2 3 4 5 6 7 
0:   0 @ P ` p
1: ! 1 A Q a q
2: " 2 B R b r
3: # 3 C S c s
4: $ 4 D T d t
5: % 5 E U e u
6: & 6 F V f v
7: ´ 7 G W g w
8: ( 8 H X h x
9: ) 9 I Y i y
A: * : J Z j z
B: + ; K [ k {
C: , < L \ l |
D: - = M ] m }
E: . > N ^ n ~
F: / ? O _ o DEL
```

- 08/08: BS
- 09/09: HT
- 10/0A: LF
- 11/OB: VT
- 12/OC: FF
- 13/0D: CR

DHCP
----
- DISCOVER
- OFFER
- REQUEST
- NAK
- ACK
- RELEASE

W = A = BTU/hr
--------------
```
1   = 0.004 = 3.4
100 = 0.4   = 341
200 = 0.9   = 682
300 = 1.3   = 1024
400 = 1.7   = 1365
500 = 2.2   = 1706
1KW = 4.4   = 3412
```

RFC1918 PRIVATE ADDRESSES
-------------------------
```
10.0.0.0    - 10.255.255.255 (10.0.0.0/8)
172.16.0.0  - 172.31.255.255  (172.16.0.0/12)
192.168.0.0 - 192.168.255.255 (192.168.0.0/16)
```

DATACENTRES
-----------

http://www.colo-x.com/blog/category/datacentre-search/

PEERING
-------

https://www.peeringdb.com

http://www.robtex.com

TLDs
----
http://www.iana.org/domains/root/db

CAP THEOREM
-----------
### Consistency
All nodes see the same data at the same time

### Availability
Node failures do not prevent survivors from continuing to operate

### Partition Tolerance
The system continues to operate despite arbitrary message loss

BASH
----
### Forkbomb
```
$ :(){ :|:& };:
```

### MAC generator
```
MACADDR="52:5:$(dd if=/dev/urandom count=1 2>/dev/null | md5sum | sed 's/^\(..\)\(..\)\(..\)\(..\).*$/\1:\2:\3:\4/')"; echo $MACADDR
```

### Here string usage
```
$ command <<"EOF"
bar
baz
EOF
```

### Oneshot STD{OUT,ERR} redirect
```
$ command &> /dev/null
```

### Iterate over lines
```
$ for i in $(<file); do echo $i; done
```

### hex->dec
```
$ printf '%d\n' 0xY
```

### dec->hex
```
$ printf '%x\n' y
```

### Test if $VAR isn't set
```
$ if [[ -z $VAR ]]; then echo unset; fi
```

### Pick a random line from a file
```
shuf -n 1 file
```

### DETECT BOM
```
$ grep -l $'\xEF\xBB\xBF' <file>
```


### Remove BOM
```
sed -i '1 s/^\xef\xbb\xbf//' <file>
```

APACHE
------
### Scoreboard key
```
. Open slot
C Closing connection
D DNS lookup
G Gracefully finishing
I Idle cleanup 
K Keepalive (read)
L Logging
R Reading request
S Starting up
W Sending reply
_ Waiting for connection
```

ESXI
----
Free key: JN0AM-4EK54-58E30-0132K-91300

PS
--
```
D    Uninterruptible sleep (usually IO)
R    Running or runnable (on run queue)
S    Interruptible sleep (waiting for an event to complete)
T    Stopped, either by a job control signal or because it is being traced.
W    paging (not valid since the 2.6.xx kernel)
X    dead (should never be seen)
Z    Defunct ("zombie") process, terminated but not reaped by its parent.
```

For BSD formats and when the stat keyword is used, additional characters may be displayed

```
<    high-priority (not nice to other users)
N    low-priority (nice to other users)
L    has pages locked into memory (for real-time and custom IO)
s    is a session leader
l    is multi-threaded (using CLONE_THREAD, like NPTL pthreads do)
+    is in the foreground process group
```

ACTIVE DIRECTORY USERACCOUNTCONTROL
-----------------------------------
```
1        - script
2        - accountdisable
8        - homedir_required
16       - lockout
32       - passwd_notreqd
64       - passwd_cant_change
128      - encrypted_text_pwd_allowed
256      - temp_duplicate_account
512      - normal_account
2048     - interdomain_trust_account
4096     - workstation_trust_account
8192     - server_trust_account
65536    - dont_expire_password
131072   - mns_logon_account
262144   - smartcard_required
524288   - trusted_for_delegation
1048576  - not_delegated
2097152  - use_des_key_only
4194304  - dont_req_preauth
8388608  - password_expired
16777216 - trusted_to_auth_for_delegation
```

LDAP RESPONSES
--------------
- 525 - user not found
- 52e - invalid credentials
- 530 - not permitted to log on at this time
- 531 - not permitted to log on at this workstation
- 532 - password expired
- 533 - account disabled
- 701 - account expired
- 773 - user must reset password
- 775 - user account locked

INITRD
------
### Open
```
$ gunzip initrd.gz
$ mkdir foo; cd foo
$ cpio -i < ../initrd
```

### Close
```
$ find | cpio -H newc -o > ../initrd.new
$ gzip -9 ../initrd.new
```

ROUTE FLAGS
-----------
```
U route is up
H target is a host
G use gateway
R reinstate route for dynamic routing
D dynamically installed by daemon or redirect
M modified from routing daemon or redirect
A installed by addrconf
C cache entry
! reject route
```

BONNIE
------
```
$ bonnie++ -n 512 -u nobody | tee bar | tail -1 | awk -F, 'BEGIN { OFS="," } {print $8,$10,$12,$14,$16,$18,$25,$27,$29,$31,$33,$35}'
```

EXT3 STRIDE/STRIPE-WIDTH
------------------------
stride = raid chunk size / fs block size
e.g
raid chunk      = 128k
fs block (ext3) = 4k
stride          = 32

stripe-width = stride * data disks.

raid1 = 1
raid5 = (n-1)

VARNISH
-------
### Clean up redundant VCLs
```
$ for i in $(varnishadm -T0:6082 vcl.list | awk '/^available/ {print $NF}'); do varnishadm -T0:6082 vcl.discard $i && echo $i; done
```

### varnishstat
```
client_conn                                - client connections 
client_req                                 - client requests (multiple requests possible in a single connection)
backend_fail                               - failed requests to a backend
backend_toolate / Backend conn. was closed - a persistent connection was closed
backend_reuse                              - a persistent connection was reused
n_object                                   - number of cached objects
n_wrk                                      - current number of worker threads
n_wrk_create                               - number of threads created (should ideally == n_wrk), if not increase the pool size
n_wrk_failed                               - threads that failed to create 
n_wrk_max / N worker threads limited       - threads that varnish wasn't allowed to create (due to max threads limit or thread_pool_add_delay)
n_wrk_overflow                             - request that had to sit in the queue because a worker wasn't available (bad)
n_wrk_drop                                 - requests that varnish rejected because the queue was full (very bad)
n_lru_nuked                                - objects that were forced from the cache due to space (rather than ttl) constraints
```

SVN
---
### Revert a revision
```
$ svn merge -c-$REVISION . [--dry-run]
```

GNUPLOT
-------
### To process CSVs
```
gnuplot> set datafile separator ','
```

### To plot data in a file
```
gnuplot> plot 'file' using 1:2
```

### Plot dots rather than crosses
```
gnupplot> plot 'file' using 1:2 with dots
```

### Vary colour depending on third field
```
gnuplot> plot 'file' using 1:2:3 linecolor variable
```

### X-axis as time
```
gnutplot> set xdata time
gnutplot> set timefmt '<strftime>' <-- field format 
gnutplot> set format x '<strftime>' <-- display format
```

### Set labels/titles
```
gnuplot> set xlabel "Foo"
gnuplot> set ylabel "Bar"
gnuplot> set title "Foobar"
```

### Logarithmic scale
```
gnuplot> set logscale y
gnuplot> unset logscale y
```

### Range
```
gnuplot> set yrange[min:max]
```

### Plot multiple fields
```
gnuplot> plot 'file' using 1:2 title "a", 'file' using 1:3 title "b"... etc
```

SOCAT
-----
### Bridge 0.0.0.0:12345 to 1.2.3.4:54321
```
$ socat TCP4-LISTEN:12345,reuseaddr,fork TCP4:1.2.3.4:54321
```

AWK
---
### Return unique results from unsorted list
```
$ awk '{if (!a[$0]++) print}'
```

### Return non-unique results from unsorted list
```
$ awk '{if (x[$3]++>0) print}'
```

### Timestamp each line: (requires gawk)
```
$ awk '{ print strftime("%Y-%m-%d %H:%M:%S"), $0; }'
```

SED
---
### Remove empty lines from a file
```
$ sed '/^$/d' file
```

NETSTAT
-------
### Display socket inode numbers (useful for matching to /proc/<pid>/fd/ entries):
```
$ netstat -e
```

SITES
-----
www.passwordcard.org - unique grid of characters, used to safely store a password in plain sight

DIKM
----
### Data
Metrics - 10 req/sec

### Information
What? - 10 req/sec for system x

### Knowledge
How? - 10 req/sec for system x is good

### Wisdom
Clarity through experience, understanding of consequences - 10 req/sec for system x is good because

FALLACIES OF DISTRIBUTED COMPUTING
----------------------------------
- The network is reliable
- Latency is zero
- Bandwidth is infinite
- The network is secure
- Topology doesn't change
- There is one administrator
- Transport cost is zero
- The network is homogeneous

PERL
----
### Paragraph grep
```
$ perl -00 -ne 'print if /foo/'
```

### Print everything between two strings
```
$ perl -ne 'print if (m!^Foo! ... m!Bar!)'
```

### Slurp entire file
```
$ perl -0777
```

EXIM
----
### Test address processing
```
$ exim -bt [-d] 
```

### Test address (from POV of <ip> - full smtp)
```
$ exim -bh <ip> [-d]
```

### Test config
```
$ exim -bV
```

### Test delivering a mail
```
$ exim -v
```

### Foreground debug
```
$ exim -bd -d
```

GIT
---
### Reset current branch to master (discard changes)
```
$ git fetch --all
$ git reset --hard origin/master
```

### See commits that haven't been pushed
```
$ git log origin..
```

PROGRAMMING TYPES
-----------------
- Static: Int foo = 1
- Dynamic: foo = 1

- Weak:   foo = foo + "a" -- foo = "1a"
- Strong: foo = foo + "a" -- fail

STP
---
- Disabled
- Blocking
- Listening
- Learning
- Forwarding

IPROUTE2
--------
```
ifconfig -> ip addr / ip link
route    -> ip route
arp      -> ip neigh
iptunnel -> ip tunnel
ipmaddr  -> ip maddr
netstat  -> ss
```

SYSLOG
------
### Facility
```
0  kernel messages
1  user-level messages
2  mail system
3  system daemons
4  security/authorization messages
5  messages generated internally by syslogd
6  line printer subsystem
7  network news subsystem
8  UUCP subsystem
9  clock daemon
10 security/authorization messages
11 FTP daemon
12 NTP subsystem
13 log audit
14 log alert
15 clock daemon (note 2)
16 local use 0  (local0)
17 local use 1  (local1)
18 local use 2  (local2)
19 local use 3  (local3)
20 local use 4  (local4)
21 local use 5  (local5)
22 local use 6  (local6)
23 local use 7  (local7)
```

### Severity
```
0 Emergency: system is unusable
1 Alert: action must be taken immediately
2 Critical: critical conditions
3 Error: error conditions
4 Warning: warning conditions
5 Notice: normal but significant condition
6 Informational: informational messages
7 Debug: debug-level messages
```

```
PRIORITY = ( FACILITY * 8 ) + SEVERITY

e.g
kernel.emergency = ( 0 * 8 )  + 0 = 0
local7.debug     = ( 23 * 8 ) + 7 = 191
```

HPACUCLI
--------
```
> ctrl slot=3 create type=logicaldrive drives=allunassigned raid=1+0 arrayaccelerator=enable
```

LAWS, PRINCIPLES AND PHENOMENA
------------------------------
### Baader Meinhoff
Experiencing something shortly after learning it

### Benford's Law
http://www.rexswain.com/benford.html

### Brooks' Law
Adding manpower to a late project makes it later

### Dunning-Kruger
Dumb people think they're smart, smart people think they're dumb.

### Pareto Principle
80/20 - 80% of effects from 20% of causes

### Parkinson's Law
People are promoted to the level of their incompetence

### Postel's law
Be conservative in what you send, liberal in what you receive

### Waterbed theory
Eliminating something (e.g complexity) in one place requires it to be added somewhere else

### Hawthorne/observer effect
Individuals modify/improve performance in response to being observed.

PROGRAMMER'S VIRTUES
--------------------
### Laziness
The quality that makes you go to great effort to reduce overall energy
expenditure. It makes you write labor-saving programs that other people will
find useful, and document what you wrote so you don't have to answer so many
questions about it. Hence, the first great virtue of a programmer. 

### Impatience
The anger you feel when the computer is being lazy. This makes you write
programs that don't just react to your needs, but actually anticipate them. Or
at least pretend to. Hence, the second great virtue of a programmer. 

### Hubris
Excessive pride, the sort of thing Zeus zaps you for. Also the quality that
makes you write (and maintain) programs that other people won't want to say bad
things about. Hence, the third great virtue of a programmer. 

SSH
---
### Don't care about remote key:
```
$ ssh -o StrictHostKeyChecking=no -oUserKnownHostsFile=/dev/null user@host
```

SSH AUTHORIZED_KEYS
-------------------
Config is placed (comma-separated) at the start of the line, e.g

```
from="10.11.12.13",command="/usr/bin/foo",no-pty ssh-rsa ABC123 comment
```

### command="foo"
Run command 'foo' when this key is used, regardless of what the user requested.
Command user passed is available through $SSH_ORIGINAL_COMMAND

### environment="FOO=bar"
Set environment variable FOO to 'bar'

### from="pattern-list"
Only allow this key to be used from hosts specified. [*?] available as wildcards. Comma-separated

### no-agent-forwarding
Don't allow client to forward their ssh agent

### no-port-forwarding
Don't allow client to forward ports

### no-pty
Don't allocate a PTY to connection

### no-user-rc
Don't execute user's .ssh/rc file

### no-X11-forwarding
Don't allow X11 forwarding

BIG O NOTATION
--------------
```
O(1)       - Constant
O(log n)   - Logarithmic
O(n)       - Linear
o(n log n) - Linearithmic / loglinear
O(n^2)     - Quadratic
O(n^3)     - Cubic
O(n!)      - Factorial
O(n^n)     - Exponential
```

Akamai Test Headers
-------------------
(comma-separated in a Pragma: header)

```
akamai-x-cache-on
akamai-x-cache-remote-on
akamai-x-check-cacheable
akamai-x-get-cache-key
akamai-x-get-extracted-values
akamai-x-get-nonces
akamai-x-get-ssl-client-session-id
akamai-x-get-request-id
akamai-x-get-true-cache-key
akamai-x-serial-no
X-Akamai-Edgescape
```
```
Pragma: akamai-x-cache-on,akamai-x-cache-remote-on,akamai-x-check-cacheable,akamai-x-get-cache-key,akamai-x-get-true-cache-key,akamai-x-get-extracted-values,akamai-x-get-nonces,akamai-x-get-ssl-client-session-id,akamai-x-serial-no,akamai-x-get-request-id,X-Akamai-Edgescape
```

ORDERS OF MAGNITUDE
-------------------
```
10^-24 yocto (y)
10^-21 zepto (z)
10^-18 atto  (a)
10^-15 femto (f)
10^-12 pico  (p)
10^-9  nano  (n)
10^-6  micro (u)
10^-3  milli (m)
10^3   kilo  (k)
10^6   mega  (M)
10^9   giga  (G)
10^12  tera  (T)
10^15  peta  (P)
10^18  exa   (E)
10^21  zetta (Z)
10^24  yotta (Y)
```

DATACENTRE TIERS
----------------
### Tier 1
Single non-redundant distribution path serving the IT equipment
Non-redundant capacity components
Basic site infrastructure guaranteeing 99.671% availability

### Tier 2
Meets or exceeds all Tier 1 requirements
Redundant site infrastructure capacity components guaranteeing 99.741% availability

### Tier 3    
Meets or exceeds all Tier 1 and Tier 2 requirements
Multiple independent distribution paths serving the IT equipment
All IT equipment must be dual-powered and fully compatible with the topology of a site's architecture
Concurrently maintainable site infrastructure guaranteeing 99.982% availability

### Tier 4     
Meets or exceeds all Tier 1, Tier 2 and Tier 3 requirements
All cooling equipment is independently dual-powered, including chillers and heating, ventilating and air-conditioning (HVAC) systems
Fault-tolerant site infrastructure with electrical power storage and distribution facilities guaranteeing 99.995% availability

AAA
---
- Authentication: Who are you?
- Authorisation: Can you access this?
- Accounting: What have you done?

METASYNTACTIC VARIABLES
-----------------------
- foo
- bar
- baz
- qux
- quux
- corge
- grault
- garply
- waldo
- fred
- plugh
- xyzzy
- thud

PRINTF
------
### Placeholders
```
%% literal %
%s string
%d signed int (decimal)
%u unsigned int (decimal)
%o unsigned int (octal)
%x unsigned int (hex)
%e floating-point, sci
%f floating-point, fixed-decimal
%g floating-point, %e or %f as appropriate
```

### Flags
```
space - prefix non-negative number with space
+     - prefix non-negative number with a plus sign
-     - left-justify
0     - use zeros to right-justify
#     - prefix 0 for oct, 0x for hex
```

### min-width
```
"<%s>", a  = "<a>"
"<%6s>", a = "<     a>"
```

### max-width / precision:
```
"<%f>", 1   = "<1.000000>"
"<%.1f>", 1 = "<1.0>"
"<%.0f>", 1 = "<1>"
```

IPTABLES
--------
### Redirect one port to another locally:
```
$ iptables -t nat -I PREROUTING -p tcp --dport <from> -j REDIRECT --to-port <to>
```

MYSQL
-----
### Skip transaction on slave
```
mysql> set GLOBAL sql_slave_skip_counter = 1; start slave;
```

### Lock waits / deadlocks
```
mysql> select * from INFORMATION_SCHEMA.INNODB_TRX
mysql> select * from INFORMATION_SCHEMA.INNODB_LOCK_WAITS
mysql> select * from INFORMATION_SCHEMA.INNODB_LOCKS
mysql> SHOW ENGINE INNODB STATUS
```

NETMASKS
--------
```
Bits  Mask             Addresses (inc net/bcast)
32    255.255.255.255  1
31    255.255.254.254  2
30    255.255.255.252  4
29    255.255.255.248  8
28    255.255.255.240  16
27    255.255.255.224  32
26    255.255.255.192  64
25    255.255.255.128  128
24    255.255.255.0    256
23    255.255.254.0    512
22    255.255.252.0    1,024
21    255.255.248.0    2,048
20    255.255.240.0    4,096
19    255.255.224.0    8,192
18    255.255.192.0    16,384
17    255.255.128.0    32,768
16    255.255.0.0      65,536
...
8     255.0.0.0        16,777,216
```

USEFUL NUMBERS
--------------
```
Seconds in a day:   86400
Minutes in a day:   1440
Seconds in a week:  604800
Minutes in a week:  10080
Largest 32-bit uint: 4294967295
Largest 64-bit uint: 18446744073709551615
```

STATS
-----
- Poisson mean
- Holt-Winters
- Pearson product-moment correlation coefficient
- 3-sigma
- Kolmogorov-Smirnov

KONAMI CODE
-----------
```
Up
Up
Down
Down
Left
Right
Left
Right
B
A
```

LATENCY
-------
(distance in km) / 200,000 * 1000 * 2 = minimum RTT
assumes light in fibre = 66% c

x 2 for 'likely' latency

EMAIL TEST STRINGS
------------------
### Virus (EICAR)
```
X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*
```

### Spam (GTUBE)
```
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

VMWARE
------

### Escape from visual console
```
CTRL-ALT
```

ILO
---
### Escape from textcons
```
ESC-(
```

VIRTUALBOX
----------
### Start VM (gui/headless)
```
$ VBoxManage startvm <name> --type (gui|headless)
```

TCP Throughput
--------------
```
bits/sec                  = window_size(bits) / latency(s)
optimal_window_size(bits) = bps * latency(s)
max_rtt(usec)             = window_size(bits) / throughput(bps)
```

AWS INSTANCE TYPES
------------------
```
T - General purpose (shared cores)
M - General purpose (dedicated cores)
C - Compute optimised
R - Memory optimised
G - Graphics/GPU equipped
I - High IOPS
D - Dense storage
```

ELASTICSEARCH
-------------
### Shard status
```
$ curl http://localhost:9200/_cat/shards?pretty
```

### Cluster health
```
$ curl http://localhost:9200/_cluster/health?pretty=true
```

### List indices
```
$ curl http://localhost:9200/_cat/indices
```

### List nodes
```
$ curl http://localhost:9200/_cat/nodes
```

### Delete index (supports wildcards)
```
curl -XDELETE http://localhost:9200/<index>
```

POSTFIX
-------
### View queue
```
$ mailq
```

### Clear all queues
```
$ postsuper -d ALL
```

### Flush (retry) queue
```
$ postfix flush
```

Q&A
---
### cifs mount fails, dmesg shows "CIFS VFS: cifs_mount failed w/return code = -22"
Ensure cifs package is installed (cifs-utils)

RABBITMQ
--------
### Create user
```
$ rabbitmqctl add_user <user> <pass>
```

### Allow to administer/log on to console
```
$ rabbitmqctl set_user_tags <user> administrator
```

### Allow config/write/read to all queues
```
$ rabbitmqctl set_permissions -p <vhost> <user> '.*' '.*' '.*'
```

UNIX PHILOSOPHY
---------------
1. Rule of Modularity: Write simple parts connected by clean interfaces.
1. Rule of Clarity: Clarity is better than cleverness.
1. Rule of Composition: Design programs to be connected to other programs.
1. Rule of Separation: Separate policy from mechanism; separate interfaces from engines.
1. Rule of Simplicity: Design for simplicity; add complexity only where you must.
1. Rule of Parsimony: Write a big program only when it is clear by demonstration that nothing else will do.
1. Rule of Transparency: Design for visibility to make inspection and debuggingeasier.
1. Rule of Robustness: Robustness is the child of transparency and simplicity.
1. Rule of Representation: Fold knowledge into data so program logic can be stupid and robust.
1. Rule of Least Surprise: In interface design, always do the least surprising thing.
1. Rule of Silence: When a program has nothing surprising to say, it should say nothing.
1. Rule of Repair: When you must fail, fail noisily and as soon as possible.
1. Rule of Economy: Programmer time is expensive; conserve it in preference to machine time.
1. Rule of Generation: Avoid hand-hacking; write programs to write programs when you can.
1. Rule of Optimization: Prototype before polishing. Get it working before you optimize it.
1. Rule of Diversity: Distrust all claims for “one true way”.
1. Rule of Extensibility: Design for the future, because it will be here sooner than you think.
