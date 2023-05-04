# How to Use cURL with Proxy?
**cURL** is a command line tool for sending and receiving data using the URL. When you enter a URL that blocked for your location or you want to hide your IP address, you need to connect proxy for cURL. Next, let’s learn how to use [cURL with proxy](https://yilu.us/integration/how-to-use-curl-with-proxy).
[![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-setting-with-yilu-proxy-1.png)](https://www.youtube.com/watch?v=5z8NjBB3n4g)
## 1. Download and install cURL.  
### A. Download cURL  
cURL official website download URL: https://curl.se/download.html  
cURL supports Windows, Linux, macOS, and here I use Windows-64bit.  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-download-into-windows-64-bit-system-2.png)
### B. Unzip the file.  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-unzip-file-3.png)  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-unzip-file-4.png)
### C. Configure environment variables  
**a. Right-click this PC, click "Properties".**  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-click-pc-properties-5.png)  
**b. Enter "Advanced system settings".**  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-properties-to-advanced-system-settings-6.png)  
**c. Enter "Advanced", click "Environment Variables".**  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-advanced-environment-variables-7.png)  
**d. Add a new user variable.**  
-Click "New"  
-Enter new user variable name: **CURL_HOME**  
-Enter variable value: enter the CURL bin file installation directory, here is `D:\Software\curl-8.0.1_7-win64-mingw\bin`  
-Click "OK" to save.  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-Add-a-new-user-variable-8.png)  
**e. Edit system variable path.**  
-Select the Path variable  
-Click "Edit"  
-Click "New"  
-Enter "**%CURL_HOME%\I386**"  
-Click "OK" to save.  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-Add-system-variable-path-10.png)  
### D. Check cURL installation status. 
On the computer keyboard, press "Windows" and "R" at the same time to open "Run" box.  
Then enter "cmd", and click "OK" to open [Command Prompt].  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/Check-cURL-installation-status-11.png)  
Enter "curl --version" to check the installation status.  
If some curl information appears, that means the CURL’s installation has been successful.  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-check-the-installation-status-12.png)  

## 2. cURL set proxy commands.
This is cURL command with proxy:  
`-x, --proxy [protocol://]host[:port]`  
Here I use "https:ipinfo.io" to test proxy IP address.  
We can use `curl -x` or `curl --proxy` to set proxy.  

For example: the following two CURL commands is the same.  
`curl -x "http://username:password@ip:port" "https://ipinfo.io"`  
or  
`curl --proxy "http://username:password@ip:port" "https://ipinfo.io"`  

**cURL default proxy protocol type is HTTP.**  
For example: the following two cURL commands is the same.  
`curl -x "http://username:password@ip:port" "https://ipinfo.io"`  
or  
`curl -x "username:password@ip:port" "https://ipinfo.io"`  

If you want to ignore or bypass proxy, use cURL noproxy command:  
`curl --noproxy "*" "https://ipinfo.io"`  

Here are some cURL commands to connect YiLuProxy different types of IPs.  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/cURL-commands-13.png)

The following content is cURL with proxy example, including set cURL HTTP proxy and cURL Socks5 proxy. Here I use [**YiLu Proxy**](https://yilu.us) as cURL proxy, and it supports Socks5 and HTTP protocols.  
### A. Username and password authorization (For YiLu Proxy dynamic IP and mobile IP)
#### ①`curl -x "http://username:password@ip:port" "https://ipinfo.io"`
a. On the YiLu Proxy [Residential IPs] or [Pro Mobile IP] tab;  
b. Select a YiLu Proxy IP type: dynamic rotating residential IP or datacenter IP, mobile IP, or Pro residential IP;  
c. Select the [username:password@IP:port] format;  
d. Set the number of generating IPs;  
e. Select a country, state, and city;  
f. Refresh;  
g. Right-click an IP;  
h. Copy IP and Port;  
i. Enter the curl proxy command; press Enter.  
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/username-and-password-authorization-14.png)
#### ②`curl -x "username:password@ip:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-2-x-username-password-ip-port-16.png)
#### ③`curl --proxy "http://username:password@ip:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-3-proxy-17.png)
#### ④`curl --proxy "username:password@ip:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-4-proxy-18.png)
#### ⑤`curl -x "socks5://username:password@ip:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-5-x-socks5-19.png)
#### ⑥`curl --proxy "socks5://username:password@ip:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-6-proxy-socks5-20.png)
#### ⑦`curl --socks5 "ip:port" "https://ipinfo.io" --proxy-user username:password`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-7-socks5-ip-port-21.png)

### B. Local port forward (for all YiLu Proxy IPs).
**During using the proxy forward port, YiLuProxy client must be running.**
For local port forwarding detailed tutorial, please view https://yilu.us/configuration/yilu-proxy-ip-use-tutorial.
#### ⑧`curl --socks5 "127.0.0.1:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-8-local-port-forward-127001-22.png)
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-8-check-local-port-forward-127001-23.png)
#### ⑨`curl --proxy "socks5://127.0.0.1:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-9-proxy-socks5-127001-24.png)
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-variable-command-9-check-proxy-socks5-127001-25.png)
#### ⑩`curl -x "socks5://127.0.0.1:port" "https://ipinfo.io"`
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/curl-command-10-x-socks5-127001-26.png)
![cURL with Proxy](https://api.yilu.us/wp-content/uploads/2023/04/Curl-command-10-check-x-socks5-127001-27.png)

The article is from https://yilu.us/integration/how-to-use-curl-with-proxy
