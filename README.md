Statische IPv4-Vergabe im FFOD-DHCP


Statische IPs muessen im Netz 10.144.1.0/21 sein!

Bitte Pull-Requests schicken!

Wenn ihr auch statische IPs an eure MAC gebunden haben wollt, macht einen fork, fuegt euch in die static.conf hinzu (nach IP sortiert!) und macht einen pull-request.




Anleitung fürs Gateway:

useradd -m -s /bin/bash dhcpstatic

cd /home/dhcpstatic

git clone https://github.com/ffod/dhcp-static.git

chown dhcpstatic:dhcpstatic dhcp-static -R

chmod +x dhcp-static/updateStatic.sh

/home/dhcpstatic/dhcp-static/updateStatic.sh

*/5 * * * * dhcpstatic /home/dhcpstatic/dhcp-static/updateStatic.sh > /dev/null 2>&1
