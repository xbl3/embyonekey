### embyonekey

Qunhui emby suite version server 1.5 key Bai Yan
-Click on the left and click on the right

# Talk ahead
You won't mess with anything
<br/> So ~~~
<br/> Please ensure that no new virtual host is created in Web Station
<br/> Please follow the instructions to set the path correctly
<br/> I am not responsible for any problems.
<br/> Can't see the picture or the script can't be downloaded and run
<br/> Scientifically good raw.githubusercontent.com URL

### Step Description
<br/> 0. Install Web Station and EMBY in Qunhui
<br/> 1. Open Web Station and create a new virtual host as shown
<br> <img src = "https://github.com/s1oz/embyonekey/blob/master/webstation.png"> <br>
<br/> 2. Open Qunhui Control Panel-Security-Certificate
<br/> Click New-Add New Certificate-Import Certificate-Select the downloaded private key and certificate
<br/> Certificate download address
`` `
https://raw.githubusercontent.com/s1oz/embyonekey/master/mb3admin.com.cert.pem
https://raw.githubusercontent.com/s1oz/embyonekey/master/mb3admin.com.key.pem
`` `
<br> <img src = "https://github.com/s1oz/embyonekey/blob/master/cert0.png"> <br>
<br/> 3. After saving, set the mb3admin.com certificate to the one just imported in the configuration
<br> <img src = "https://github.com/s1oz/embyonekey/blob/master/cert1.png"> <br>


#### Hijack mb3admin pseudo-station

If the NAS address of the fake station is 10.0.0.10, fill it in as follows, and modify it according to your actual situation.The purpose is to hijack the domain name to the fake station.

    10.0.0.10 mb3admin.com
	
If you are using ipv6, please add the ipv6 address together, you can avoid Bai Sheng sometimes effective and sometimes invalid
<br/> OP. Fill in the IPv6 ULA prefix in the network-interface-global network options
<br/>! [] (https://github.com/s1oz/embyonekey/blob/master/ULA.png)
<br/> If mine is fd59: 5890: 1be9 :: / 48 The IP of the pseudo-station is 10.0.0.10, and the end is 10, so fill in as follows
	
    fd59: 5890: 1be9 :: 10 mb3admin.com
	
<br/> If you hijack the main route, you can directly modify the hosts without other settings
<br/> If there is a bypass, you may need to modify the hosts on the bypass (maybe, not tried)
<br/> If there is no route hijacking, you need to modify to hijack each client to the pseudo station

0. OP Merlin routing can directly modify the hosts file in the routing
<br/> Log into ssh and enter the following command
`vi / etc / hosts`
<br/> i enter edit state
<br/> Add `10.0.0.10 mb3admin.com`
`: wq` save and exit
<br/> Log in OP-network-DHCP / DNS-HOSTS and parse the file to save and apply
1. Qunhui can directly log in to modify
<br/> Log into ssh and enter the following command
`vi / etc / hosts`
<br/> i enter edit state
<br/> Enter `10.0.0.10 mb3admin.com`
`: wq` save and exit
2. Windows modification is just a different path
<br/> Open the `C: \ Windows \ System32 \ drivers \ etc \` directory directly
<br/> Modify the hosts file in the folder
	
### Next run this script


Run the command as the root user: <br/>
</ p> <pre> <code> wget -N --no-check-certificate "https://raw.githubusercontent.com/s1oz/embyonekey/master/embyonekey.sh" && chmod + x embyonekey.sh &&. /embyonekey.sh</code> </ pre>

<br/> Completed
<br/> You can enter the following command to test
`` `
nginx -t
`` `
Check if an error is reported

`` `
curl https://mb3admin.com/admin/service/registration/validateDevice
curl https://mb3admin.com/admin/service/registration/validateDevice/666
`` `
Run the command in ssh to check whether the return value is correct

#### I wish you all fun

<br/> As shown in the picture, open to have a member yellow label
<br/>
<br/>! [] (https://github.com/s1oz/embyonekey/blob/master/ko.png)
<br/>
<br/> Enter any key in Emby Premiere to activate successfully
<br/>
<br/>! [] (https://github.com/s1oz/embyonekey/blob/master/ko1.png)

#### Client certificate installation
If the server fails to display correctly, the client still cannot be displayed correctly, generally the certificate is incorrect, please install the certificate on the client
`` `
https://raw.githubusercontent.com/s1oz/embyonekey/master/guomi.cer 
`` `
Download this certificate file named guomi.cer and install it on the corresponding device

Windows please install under this directory
<br/>! [] (https://github.com/s1oz/embyonekey/blob/master/window.png)

<br/> The IOS needs to trust the certificate in the settings-general-about mobile-certificate trust settings after installation


## Thanks to the time axis, the stars can't be magic