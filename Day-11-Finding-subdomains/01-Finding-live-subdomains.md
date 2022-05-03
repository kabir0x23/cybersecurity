### Finding subdomains + Live subdomains
Here our target is example Sony

First step is to find subdomains as much we can
our main focus must be on live subdomains

##### Installation of Tools
1. Installation of GO Language
-> https://go.dev/doc/install
2. Installation of Tools (subdomains finders)
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install github.com/projectdiscovery/httpx/cmd/httpx@latest
go install github.com/tomnomnom/httprobe@latest

apt install amass
apt install assetfinder
pip3 install dnsgen

git clone https://github.com/aboul3la/Sublist3r.git
cd Sublist3r
sudo pip install -r requirements.txt

---
##### Hunting Subdomains
1. Subfinder:
-> subfinder -d sony.com -o subfinder_sony.com.txt
Found: 8986 subdomains.
![[images/Pasted image 20220503114800.png]]
2. Assetfinder:
-> assetfinder -subs-only sony.com | tee assetfinder_sony.com.txt
Found: 5205 subdomains.
![[images/Pasted image 20220503115834.png]]
3. Sublister:
-> python3 /opt/Sublist3r/sublist3r.py -d sony.com -o sublist3r_sont.com.txt
Found: 5513 subdomains.
![[images/Pasted image 20220503115940.png]]
4. Amass:
amass is slow tool, but its a best tool.

-> amass enum -brute -d sony.com -o amass_sony.com.txt
Found: subdomains.

Found: 1462 subdomains

![[images/Pasted image 20220503120551.png]]


We have found total 41142 subdomains using different tools
and we have found 11136 Unique Sub domains 
![[images/Pasted image 20220503125059.png]]

---
##### Hunting Dev Subdomains
Finding Dev Sub domains
like stage.sony.com 
dev.sony.com
etx 

1. Sort the Subs 
cat * | sort -u | tee combinedsubs_sony.com.txt

2. run Dnsgen
dnsgen combinedsubs_sony.com.txt | tee devsubs_sony.com.txt 
Found more than 602439466 sub domains
![[images/Pasted image 20220503132341.png]]

---
##### Hunting Live Subdomains
Now Lets find (working) live subdomains
these both will going to take much time acc to the size of dev domains
If you have vps then good to go 
1. Httpx
-> cat dnsgen_sony.com.txt | httpx -o httpx_subs_sony.com.txt
![[images/Pasted image 20220503200729.png]]

2. Httprobe
-> cat dnsgen_sony.com.txt | httprobe | tee httprobe_sony.com.txt
![[images/Pasted image 20220503201117.png]]

Now combine the both results and sort it 
cat http* | sort -u | tee live_subs_sony.com.txt

---
Go to https://chaos.projectdiscovery.io/#/
you will find bunch of live domains
just download and start hacking 😉.
Found 19996 Sub domains.

![[images/Pasted image 20220503134801.png]]
![[images/Pasted image 20220503134823.png]]