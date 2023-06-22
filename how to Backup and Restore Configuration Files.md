enable

The prompt changes toRouter#, which indicates that the router is now in privileged mode.

Copy this configuration file to the TFTP server:
```
CE_2#copy running-config tftp:
Address or name of remote host []? 10.104.207.171
Destination filename [ce_2-confg]? backup_cfg_for_my_router
!!
1030 bytes copied in 2.489 secs (395 bytes/sec)
CE_2#
```
Open the configuration file with a text editor. Search for and remove any line that starts with "AAA".

Copy the configuration file from the TFTP server to a new router in privileged (enable) mode which has a basic configuration.
```
Router#copy tftp: running-config
Address or name of remote host []? 10.104.207.171
Source filename []? backup_cfg_for_my_router
Destination filename [running-config]?
Accessing tftp://10.66.64.10/backup_cfg_for_my_router...
Loading backup_cfg_for_router from 10.104.207.171 (via FastEthernet0/0): !
[OK - 1030 bytes]

1030 bytes copied in 9.612 secs (107 bytes/sec)
CE_2#
```
## Use an FTP Server to Backup and Restore a Configuration

At theRouter>prompt, issue theenablecommand, and provide the required password when prompted.

The prompt changes toRouter#, which indicates that the router is now in privileged mode.

Configure the FTP username and password.
```
CE_2#configure terminal
CE_2(config)#ip ftp username cisco
CE_2(config)#ip ftp password cisco123
CE_2(config)#end
CE_2#
```
Copy the configuration to the FTP server.
```
CE_2#copy running-config ftp:
Address or name of remote host []? 10.66.64.10
Destination filename [ce_2-confg]? backup_cfg_for_router
Writing backup_cfg_for_router !
1030 bytes copied in 3.341 secs (308 bytes/sec)
CE_2#
```
Open the configuration file with a text editor. Search for and remove any line that starts with "AAA".

Copy the configuration file from the FTP server to a router in privileged (enable) mode which has a basic configuration.

```
Router#copy ftp: running-config
Address or name of remote host [10.66.64.10]? 
Source filename [backup_cfg_for_router]? 
Destination filename [running-config]? 
Accessing ftp://10.66.64.10/backup_cfg_for_router...
Loading backup_cfg_for_router !
[OK - 1030/4096 bytes]
1030 bytes copied in 13.213 secs (78 bytes/sec)
CE_2#

```
