# ZAP Proxy

* OWASP (Open Web Application Security Project) is worldwide non-profit organization focused on improving the security of software.

* OWASP ZAP (Zed Attack Proxy) is one of the world’s most popular security tool.


![1](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bb/Proxy_concept_en.svg/1200px-Proxy_concept_en.svg.png)


![1](https://img.wonderhowto.com/img/63/85/63563817867426/0/sploit-make-proxy-server-python.1280x600.jpg)




* [ZAP - Setting up ZAP for Browser](https://www.youtube.com/watch?time_continue=132&v=Uin07SHkQTE)

# 1. Setting up your ZAP Environment
* 1.1 JAVA 8+ : In order to install ZAP you need to install JAVA 8+ to your Windows or Linux system.
* 1.2 Download ZAP from here - https://github.com/zaproxy/zaproxy/wiki/Downloads
* 1.3 Install and open ZAP  

# Starting OWASP ZAP

The default install directory **C:\Program Files\OWASP\Zed Attack Proxy\ZAP.exe**

* As it is a Java application, alternatively you can run the following command to start it. What it gives you extra configuration like scheduling your penetration test or starting with a particular URL.

* **java -Xmx512m -jar zap-2.7.0.jar**




# 2. Configuring Proxy
## 2.1 Setup Proxy in Zap
* In the ZAP UI, go to Tools>Options>Local Proxy
* Make sure the port is set to 8080 (or the port you have configured in your browser)
* Hit the URL:, it should return Zap welcome page: https://127.0.0.1:8080
![1](https://andrewedstrom.com/assets/images/zap2.jpg)

## 2.2 Proxy Setup in the browser
* 3.2 Open your preferred browser and set up the proxy as shown here (You can use port 8080 as the port)
![1](https://security.secure.force.com/resource/1425350868000/ZapTutorialImages/ZapImages/SettingUpBrowser/images/image02.png)
* How to Change Proxy Settings: https://www.wikihow.com/Change-Proxy-Settings


# 3. Installing certificate
3.1 Go to Tools>Options>Dynamic SSL Certificate. Click Generate and then click Save.
3.2 Save the certificate in the desired location
3.3 Open your browser and install the Certificate to your browser (Firefox, Chrome, IE) accordingly 


Add the ZAP certificate to your system’s trusted certificates
Next, we need to tell our system to trust messages forwarded to us by the ZAP proxy so that we will be able to visit urls that start with https://. To do this, we need to give the Operating System the ZAP proxy’s certificate.

* https://2buntu.com/articles/1517/adding-ssl-certificates-from-owasp-zap-a-visual-walkthrough/
