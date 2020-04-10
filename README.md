<p align="center">
	<a href="https://technitium.com/dns/">
		<img src="https://technitium.com/img/logo.png" alt="Technitium DNS Server" /><br />
		<b>Technitium DNS Server</b>
	</a><br />
	<br />
	<b>Get a personal local DNS Server for privacy & security.</b><br />
	<b>Block Ads at DNS level!</b>
</p>
<p>
<img src="https://technitium.com/dns/ScreenShot1.png" alt="Technitium DNS Server" />
</p>

Technitium DNS Server is an open source tool that can be used for self hosting a local DNS server for privacy & security or, used for experimentation/testing by software developers on their computer. It works out-of-the-box with no or minimal configuration and provides a user friendly web console accessible using any web browser.

Nobody really bothers about domain name resolution since it works automatically behind the scenes and is complex to understand. Most computer software use the operating system's DNS resolver that usually query the configured ISP's DNS server using UDP protocol. This way works well for most people but, your ISP can see and control what website you can visit even when the website employ HTTPS security. Not only that, some ISPs can redirect, block or inject content into websites you visit even when you use a different DNS provider like Google DNS or Cloudflare DNS. Having Technitium DNS Server configured to use DNS-over-TLS or DNS-over-HTTPS forwarders, these privacy & security issues can be mitigated very effectively.

Developers regularly use the hosts file for configuring an IP address for a domain under testing. However, using the hosts file is cumbersome at times and can only be used to resolve domain name to an IP address. With a fully configurable DNS server running on your local machine, you can configure not just simple A records (for IP address) but, also configure other types of records like CNAME or MX etc. This allow you to have more control and power when you want to do testing that simulates the exact configuration that you have running on production.

Applications of using a locally hosted DNS server is limited only by the user's imagination!

# Features
- Works on Windows, Linux, macOS and Raspberry Pi.
- Installs in just a minute and works out-of-the-box with zero configuration.
- Block Ads using one or more block list URLs.
- Run [DNS-over-TLS](https://en.wikipedia.org/wiki/DNS_over_TLS) and [DNS-over-HTTPS](https://en.wikipedia.org/wiki/DNS_over_HTTPS) DNS service on your network.
- Use public DNS resolvers like Cloudflare, Google & Quad9 with [DNS-over-TLS](https://en.wikipedia.org/wiki/DNS_over_TLS) and [DNS-over-HTTPS](https://en.wikipedia.org/wiki/DNS_over_HTTPS) protocols as forwarders.
- Advance caching with features like serve stale, prefetching and auto prefetching.
- Supports working as an authoritative as well as a recursive DNS server.
- Host domain names on your own DNS server.
- Wildcard sub domain support.
- Enable/disable zones and records to allow testing with ease.
- Built-in DNS Client with option to import responses to local zone.
- Supports out-of-order DNS request processing for DNS-over-TCP and DNS-over-TLS protocols.
- Built-in DHCP Server that can work for multiple networks.
- IPv6 support in DNS server core.
- HTTP & SOCKS5 proxy support which can be configured to route DNS over [Tor Network](https://www.torproject.org/) or use Cloudflare's hidden DNS resolver.
- Web console portal for easy configuration using any web browser.
- Built-in system logging and query logging.
- Open source cross-platform .NET Core implementation hosted on GitHub.

# Installation
- **Windows**: [Download setup installer](https://download.technitium.com/dns/DnsServerSetup.zip) for easy installation.
- **Linux & Raspberry Pi**: Follow install instructions from [this blog post](https://blog.technitium.com/2017/11/running-dns-server-on-ubuntu-linux.html).
- **Cross-Platform**: [Download portable app](https://download.technitium.com/dns/DnsServerPortable.tar.gz) to run on any platform that has .NET Core installed.

# Help Topics
Read the latest [online help topics](https://go.technitium.com/?id=25) which contains the DNS Server user manual and covers frequently asked questions.

# Support
For support, send an email to support@technitium.com. For any issues, feedback, or feature request, create an issue on [GitHub](https://github.com/TechnitiumSoftware/DnsServer/issues).

# Become A Patron
Make contribution to Technitium by becoming a Patron and help making new software, updates, and features possible.

[Become a Patron now!](https://www.patreon.com/technitium)

# Blog Posts
- [phra's blog: Exfiltrate Like a Pro: Using DNS over HTTPS as a C2 Channel](https://iwantmore.pizza/posts/dnscat2-over-doh.html) (Aug 2019)
- [Scott Hanselman: Exploring DNS with the .NET Core based Technitium DNS Server](https://www.hanselman.com/blog/ExploringDNSWithTheNETCoreBasedTechnitiumDNSServer.aspx) (Apr 2019)
- [Technitium Blog: Turn Raspberry Pi Into Network Wide DNS Server](https://blog.technitium.com/2019/01/turn-raspberry-pi-into-network-wide-dns.html) (Jan 2019)
- [Technitium Blog: Blocking Internet Ads Using DNS Sinkhole](https://blog.technitium.com/2018/10/blocking-internet-ads-using-dns-sinkhole.html) (Oct 2018)
- [Technitium Blog: Configuring DNS Server For Privacy & Security](https://blog.technitium.com/2018/06/configuring-dns-server-for-privacy.html) (Jun 2018)
- [Technitium Blog: Technitium DNS Server v1.3 Released!](https://blog.technitium.com/2018/06/technitium-dns-server-v13-released.html) (Jun 2018)
- [Technitium Blog: Running Technitium DNS Server on Ubuntu Linux](https://blog.technitium.com/2017/11/running-dns-server-on-ubuntu-linux.html) (Nov 2017)
- [Technitium Blog: Technitium DNS Server Released!](https://blog.technitium.com/2017/11/technitium-dns-server-released.html) (Nov 2017)


Running Technitium DNS Server on Ubuntu Linux
Technitium DNS Server is build to be cross platform using the .NET Standard 2.0. You can run the DNS Server Portable App on Linux or macOS by using .NET Core. This post is written for Ubuntu Linux but, you can easily follow similar steps on your favorite distro.

This blog post is updated regularly to provide latest instructions to install the DNS Server. So, refer it when you are about to do a fresh installation.

Using Automated Installer / Updater
Automated installer script can be used to install or update the DNS Server. Automated installer script is available for following distros:

Ubuntu Server (x86 & x64)
curl -sSL https://download.technitium.com/dns/install-ubuntu.sh | sudo bash
Raspbian (Stretch) for Raspberry Pi (ARM32)
curl -sSL https://download.technitium.com/dns/install-raspi.sh | sudo bash
Installing DNS Server Manually
Install the latest .NET Core runtime from here. Start Terminal and follow the steps below to install DNS Server on Ubuntu:

Download DNS Server portable app using wget and extract it.
wget https://download.technitium.com/dns/DnsServerPortable.tar.gz
sudo mkdir -p /etc/dns/
sudo tar -zxf DnsServerPortable.tar.gz -C /etc/dns/
You can now run the DNS Server directly from console as a standalone app.
cd /etc/dns/
sudo ./start.sh
Or, if your distro uses systemd, follow these steps to install it as a daemon.
sudo cp /etc/dns/systemd.service /etc/systemd/system/dns.service
sudo systemctl enable dns.service
sudo systemctl start dns.service
You may want to check the systemd log entries to find issue if the daemon fails to start:

journalctl --unit dns --follow
Or, if your distro does not support systemd, follow these steps to run it as a daemon using supervisor.
sudo apt-get -y install supervisor
sudo cp /etc/dns/supervisor.conf /etc/supervisor/conf.d/dns.conf
sudo service supervisor restart
You may want to check the log file to find issue if the daemon fails to start:

cat /var/log/dns.err.log
Open the url http://localhost:5380/ to access the web console.
Updating DNS Server Manually
Make sure you got the latest .NET Core runtime from here. Start Terminal and follow the steps below to update DNS Server on Ubuntu:

Download DNS Server portable app using wget and extract it.
wget https://download.technitium.com/dns/DnsServerPortable.tar.gz
sudo tar -zxf DnsServerPortable.tar.gz -C /etc/dns/
If your distro uses systemd, follow these steps to restart the DNS Server daemon.
sudo systemctl restart dns.service
You may want to check the systemd log entries to find issue if the daemon fails to start:

journalctl --unit dns --follow
Or, if your distro does not support systemd, follow these steps to restart the DNS Server using supervisor.
sudo service supervisor restart
You may want to check the log file to find issue if the daemon fails to start:

cat /var/log/dns.err.log
Open the url http://localhost:5380/ to access the web console.
Common Issue With Ubuntu
If you are using Ubuntu Desktop, you may find dnsmasq or systemd-resolved daemon already running on UDP port 53 preventing the DNS Server to listen on the same port. You can check the DNS Server log file from the web console to confirm the issue by finding this error:

[2019-01-01 07:30:59 UTC] [0.0.0.0:53] System.Net.Sockets.SocketException (98): Address already in use
   at System.Net.Sockets.Socket.UpdateStatusAfterSocketErrorAndThrowException(SocketError error, String callerName)
   at System.Net.Sockets.Socket.DoBind(EndPoint endPointSnapshot, SocketAddress socketAddress)
   at System.Net.Sockets.Socket.Bind(EndPoint localEP)
   at DnsServerCore.DnsServer.Start() in Z:\Technitium\Projects\DnsServer\DnsServerCore\DnsServer.cs:line 811
You may confirm if its dnsmasq or systemd-resolved by running sudo netstat -nlpu command.

Follow these steps below to disable the dnsmasq service:

Edit the NetworkManager.conf file to disable dnsmasq service:
sudo nano /etc/NetworkManager/NetworkManager.conf
Comment out the dns=dnsmasq line by adding # character at the beginning like this #dns=dnsmasq and exit the editor by pressing CTRL+X and enter y to save the file.
Restart the computer to apply changes as shown below:
sudo reboot now
After system reboot, open Terminal and check DNS Server logs again from the web console.
Follow these steps below to disable the systemd-resolved service:

Disable the systemd-resolved service and stop it:
sudo systemctl disable systemd-resolved
sudo systemctl stop systemd-resolved
Edit your /etc/resolv.conf using nano:
sudo nano /etc/resolv.conf
Edit the existing nameserver entry to the one shown below in your /etc/resolv.conf
nameserver 127.0.0.1
Edit your /etc/NetworkManager/NetworkManager.conf using nano:
sudo nano /etc/NetworkManager/NetworkManager.conf
Put the following line in the [main] section of your /etc/NetworkManager/NetworkManager.conf as shown below:
[main]
dns=default
Restart network-manager:
sudo service network-manager restart
Now restart the DNS Server and check logs again from the web console.
sudo systemctl restart dns.service
That's it!
The DNS Server is running and you can configure your network with the IP address of this computer for DNS resolution.

Check out the web console to create zone, check cached zones, access DNS client tool and configure server settings.

The DNS Server creates a folder named config in the current folder which contains the server config and zone files. Make sure you copy this folder while moving the DNS server folder if you want all the zone files and config to persist.
