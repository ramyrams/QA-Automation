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



 # Default Startup Dialog of Owasp Zap

![](https://cdn-images-1.medium.com/max/900/1*p5deaD3oyywvFx83fLqOZQ.png)



# Modes
![](https://cdn-images-1.medium.com/max/1125/1*8RMpIlHk1tvDV69rJEaI1Q.png)

** 1. Modes:** On the upper-left of the screen you see modes. There are 4 modes;

* Standard Mode: Allows you to do anything to any website.
* Attack Mode: Active scans any websites.
* Safe Mode: Turns off all the harmful features while scanning.
* Protected Mode: Allow you to scan websites in a particular scope. It prevents you to scan an unwanted website

# Sites
![](https://cdn-images-1.medium.com/max/900/1*tYOWTi-nlbOP6tog-zJF1w.png)

 All the sites you access via the ZAP Proxy will be listed here. If your website makes a request to another website, you’ll see that under a separate site.

2.1 — Show Only URLs in Scope: You should toggle this option on because the sites section gets ugly after some test. To focus your target website in the sites you should create a new context of your website and keep In Scope option checked. By doing this you will no longer see other websites that you are not interested in.


# Workspace Window:

The workspace window consists of 3 tabs:

3.1 — Quick Start Window: It’s the direct and fastest way of starting an active scan. Enter the target website address in the URL to attack input and hit the attack button. It first crawls the website then performs active scan.

3.2 — Request & Response Window: These are the most used parts of the UI. In the request tab, you see the window is divided into 2 parts. Upper shows request’s header and cookies and the bottom shows the post parameters as being sent to server. The response windows is similar to the request window. Shows the response header and body.
![](https://cdn-images-1.medium.com/max/1125/1*Ez-q4tA2r5WvrZT-v8SmOQ.png)
![](https://cdn-images-1.medium.com/max/1125/1*YKXJ-f-w1nFE4TSZE4VnCw.png)

# Proxying Your Website: JxBrowser

In the earlier version of OWASP ZAP, you had to configure your browser’s proxy to capture requests. But there’s a new cool feature JxBrowser! This is a Chromium-based browser integrated in OWASP ZAP. By default it has all the proxy configuration set up and lets OWASP ZAP to cross all the traffic over it. Hit the Launch Browser and navigate to your website.

https://cdn-images-1.medium.com/max/900/1*I4xL_XOSp8x3NfdAZFvOIw.png


# Navigating Your Website
In order to extract the tree of your website, you need to crawl the website in JxBrowser. You should hit all the features, go thru all possible actions. This phase is very important!

** The more you explore your website, the more you get efficient results.**
