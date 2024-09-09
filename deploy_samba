!/bin/bash

dominio="DC=rsai-tipy-uy,DC=duckdns,DC=org"
ls /etc/samba
rm $(smbd -b | grep "CONFIGFILE" | cut -d ":" -f2)
echo "etc/samba/smb.conf borrado"
ls /etc/samba

apt-get install acl attr samba samba-client winbind libpam-winbind libnss-winbind dnsutils python3-setproctitle -y

for VARIABLE in $(smbd -b | egrep "LOCKDIR|STATEDIR|CACHEDIR|PRIVATE_DIR" | cut -d ":" -f2)
do
    echo "Deleting *.tdb y *.lbd on, $VARIABLE"
    rm -Rf $VARIABLE/*.tdb
    rm -Rf $VARIABLE/*.ldb
done

systemctl stop winbind smbd nmbd
systemctl disable winbind smbd nmbd

samba-tool domain provision --server-role=dc --use-rfc2307 --dns-backend=SAMBA_INTERNAL --realm=RSAI-TIPY-UY.DUCKDNS.ORG --domain=RSAI-TIPY-UY --adminpass=Passw0rd

sed -i 's/8.8.8.8/127.0.0.1/' /etc/resolv.conf

samba            

host -t SRV _ldap._tcp.RSAI-TIPY-UY.DUCKDNS.ORG                                                                         
host -t SRV _kerberos._udp.RSAI-TIPY-UY.DUCKDNS.ORG
host -t A 01-RS-samba.rsai-tipy-uy.duckdns.org
