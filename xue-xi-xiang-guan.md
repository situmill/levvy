### **1.如何在node服务端生成验证码?（2019-03-08）**

#### **a.node服务端安装：**

**1.$ npm install --save svg-captcha（生成svg图像）**

**2.$ npm install cookie-parser（保存到cookie中）**

**3.相关代码:图x1**

#### 图x1

![](/assets/x1.png)

#### **b.前端使用:**

**1.用img标签显示:**`<img src="http://{url}/captcha">`

**2.getCookie\('captcha'\)获取服务器传的验证码.**

---

---



