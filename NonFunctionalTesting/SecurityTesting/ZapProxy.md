
* [ZAP - Setting up ZAP for Browser](https://www.youtube.com/watch?time_continue=132&v=Uin07SHkQTE)

# 1. Installation
1.1 Download ZAP from here - https://github.com/zaproxy/zaproxy/wiki/Downloads
1.2 Install and open ZAP  


# 3. Configuring Proxy
## 3.1 Setup Proxy in Zap
* In the ZAP UI, go to Tools>Options>Local Proxy
* Make sure the port is set to 8080 (or the port you have configured in your browser)
* Hit the URL:, it should return Zap welcome page: https://127.0.0.1:8080
![1](https://andrewedstrom.com/assets/images/zap2.jpg)

## 3.2 Proxy Setup in the browser
* 3.2 Open your preferred browser and set up the proxy as shown here (You can use port 8080 as the port)
![1](https://security.secure.force.com/resource/1425350868000/ZapTutorialImages/ZapImages/SettingUpBrowser/images/image02.png)
* How to Change Proxy Settings: https://www.wikihow.com/Change-Proxy-Settings





# 2. Installing certificate
2.1 Go to Tools>Options>Dynamic SSL Certificate. Click Generate and then click Save.
2.2 Save the certificate in the desired location
2.3 Open your browser and install the Certificate to your browser (Firefox, Chrome, IE) accordingly 


Add the ZAP certificate to your system’s trusted certificates
Next, we need to tell our system to trust messages forwarded to us by the ZAP proxy so that we will be able to visit urls that start with https://. To do this, we need to give the Operating System the ZAP proxy’s certificate.
