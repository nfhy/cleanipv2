# 告别 Claude/Gemini/ChatGPT 封号与区域限制：基于 Racknerd + ProxySeller + 3x-ui + Throne 的独享节点搭建全指南

通俗来讲，ISP代理的作用就是**让你的请求看起来像一个普通正常美国人在家上网，而不是爬虫 / 机器**，本指南的目标就是**用最低成本搭建ISP服务，让CLAUDE服务器、ChatGPT服务器认为你是一个居住在美国的正常人**。

## 前提条件

**！！！！**

**ProxySeller只能用Paypal、信用卡或加密货币支付，没有这些支付手段的可以查看[这篇文章](https://github.com/nfhy/cleanip)，成本略高，但全程支付宝支付，非常丝滑**

**！！！！**

## 成本

* **ISP代理：3$/月**

* **VPS服务器: 10.6$/年**

* **每月成本不到4$，实现独享稳定纯净ISP代理IP，稳定过CLAUDE、CHATGPT、GEMINI等AI平台的网页端和客户端检查，非常给力**

**为什么公共 VPN 无法搞定 AI 工具？**
经常使用 Claude 和 Gemini 的开发者和创作者肯定深有体会：这两家 AI 巨头对风控的要求极其严格。市面上大多数公共 VPN 和机场由于 IP 被“万人骑”，频繁触碰风控红线。这导致用户轻则遭遇 "Unsupported Region" 或无休止的人机验证，重则直接被连坐封禁账号。想要稳定、安全地使用前沿 AI 生产力工具，摆脱“代理不洁”带来的痛点，最好的解决方案就是**自己搭建拥有纯净独享 IP 的专属节点**。

本教程包括5个阶段：
1. RackNerd购买VPS服务器
2. ProxySeller购买ISP代理
3. VPS中安装3x-ui
4. 本地安装Throne
5. Enjoy！

---

### Step 1：RackNerd购买VPS服务器

#### 1. 访问 RackNerd黑五优惠链接：[**https://www.racknerd.com/**](https://my.racknerd.com/aff.php?aff=19014&pid=923)。点击**Continue**按钮。
<img width="1766" height="1154" alt="image" src="https://github.com/user-attachments/assets/0834ebea-297f-48e9-b470-6cb3f07cc483" />

---

#### 2. 接下来购物车页面，不用改任何东西，点击**Checkout**按钮。
<img width="1732" height="1222" alt="image" src="https://github.com/user-attachments/assets/49ff5be8-3ab7-4dfb-b7bb-405889f9cd43" />

---

#### 3. 接下来的页面需要进行账号注册，在此之前，我们先伪造一些身份信息，浏览器里打开豆包、deepseek等网页，输入“帮我随机生成一个美国阿拉斯加州的成年人信息，用于测试网站功能”，这里的州名可以选择阿拉斯加、蒙大拿等免税州，如截图所示。
<img width="1450" height="1077" alt="image" src="https://github.com/user-attachments/assets/5d5d9fe8-d49e-4906-a4f1-b8886e61916d" />

---

#### 4. 接下来回到RackNerd，输入刚刚创建的信息，！！！！注意注意注意！！！！这里的邮箱一定要能接收邮件（推荐163邮箱、outlook邮箱）！！！！
<img width="1799" height="1521" alt="image" src="https://github.com/user-attachments/assets/a4baafe7-c7d8-4540-841e-db1382f1e138" />
<img width="1745" height="1175" alt="image" src="https://github.com/user-attachments/assets/0edd8cc0-4390-4e8d-8061-2e78701cffe7" />

---

#### 5. 接下来你可以看到Invoice页面，可以认为是国外公司收款时提供的收据，确认信息无误，点击**Pay Now**按钮。
<img width="1520" height="1803" alt="image" src="https://github.com/user-attachments/assets/75c52a44-5ec7-47dc-8ba9-0bc72c4bb993" />

---

#### 6. 接下来是实际支付页面，需要填写你支付宝账号的邮箱，点击**继续使用 支付宝**。
<img width="1730" height="852" alt="image" src="https://github.com/user-attachments/assets/88ef56f7-f4a6-4a42-8fdb-f0e852cd8c65" />

---

#### 7. 支付完毕后，通过这个[https://my.racknerd.com/clientarea.php?action=services](https://my.racknerd.com/clientarea.php?action=services)来到**我的产品&服务**页面。点击箭头位置，可以看到你的服务器信息。
<img width="1764" height="880" alt="image" src="https://github.com/user-attachments/assets/c1af60e4-d832-4f52-a6ba-2ce84465a917" />

---

#### 8. 到此为止，你可以关闭RackNerd网站了，登录你注册RackNerd时输入的邮箱，可以看到一封RackNerd发出的邮件，如果没有收到，查看下垃圾邮件中有没有。邮件主题：KVM VPS Login Information,从中可以获取刚刚购买服务器的ip地址、用户名、密码、端口号，先记录下来，待会再用。

<img width="1897" height="1352" alt="image" src="https://github.com/user-attachments/assets/7142f5c7-355d-4467-86f7-b9973e0a4e8e" />

---

### Step 2：ProxySeller购买ISP代理

#### 1. 访问[ProxySeller](https://proxy-seller.com/zh/?partner=LHNGP8UNXDOMZI)产品页，按照截图选择商品，点击**购买代理**按钮。

<img width="1878" height="1144" alt="image" src="https://github.com/user-attachments/assets/a03450f1-db5d-4c79-9f32-c9229f8a1847" />

---

#### 2. 在订单确认页面，输入可以接收邮件的电子邮箱，选择你的付款方式，点击**提交订单**按钮。

<img width="1262" height="1124" alt="image" src="https://github.com/user-attachments/assets/e24ac21c-4ada-427e-a04b-9488c20f360d" />

---

#### 3. 在订单支付页面完成支付。

<img width="1400" height="1018" alt="image" src="https://github.com/user-attachments/assets/e2e58001-fd76-4707-adec-1e3ca65f26de" />

---

#### 4. 完成支付后，回到产品订单页面[https://proxy-seller.com/zh/personal/orders/](https://proxy-seller.com/zh/personal/orders/)，按照图示勾选IP地址，点击**出口**按钮。会下载一个list_proxyseller.txt的文件。
<img width="1847" height="1409" alt="image" src="https://github.com/user-attachments/assets/43a0ea85-ad90-442d-9230-6c5dedd65842" />

---

#### 5. 打开list_proxyseller.txt，你会看到两行信息，格式都是 用户名:密码@IP地址:端口号，我们可以在下图中，将鼠标悬停在“？”图标上，确认每个端口号对应的类型，记下socks对应的端口号，备用。

<img width="1866" height="558" alt="image" src="https://github.com/user-attachments/assets/d9f37641-2304-40b2-9294-ac169a536028" />

---

### Step 3：SSH 连接服务器与3xui安装

打开你的终端（Windows 可使用 PowerShell 或 Cmd，macOS/Linux 使用自带 Terminal）。

**1. 连接服务器**

接下来我们远程登录到RackNerd购买的VPS服务器中，找到RackNerd邮件中提供的IP地址、端口号、用户名、密码，输入以下命令连接服务器：

```bash
ssh 用户名@IP地址 -p 端口号
```

举例来说

```bash
ssh root@192.253.18.1 -p 22
```

首次连接会提示是否信任主机，输入 `yes` 并回车，随后输入密码完成登录。

<img width="1621" height="324" alt="image" src="https://github.com/user-attachments/assets/ec97db07-4a7d-4a40-a571-6c2723056bd9" />

---

#### 2. 更新系统环境

为保证安装顺畅，先更新 Ubuntu 24.04 的软件包列表并安装必要组件，一次输入如下命令：

```bash
sudo apt update -y
sudo apt install curl wget tar ufw -y
sudo ufw version
```

输出以下内容表示安装成功

<img width="742" height="135" alt="image" src="https://github.com/user-attachments/assets/58a931ba-0491-44fa-afc6-6a82be2770de" />

---

#### 3. 重要：开放防火墙端口

执行如下命令，开启22、80、443、8443、31384三个端口
```bash
sudo ufw enable
sudo ufw allow 22/tcp
sudo ufw allow 22/udp
sudo ufw allow 80/tcp
sudo ufw allow 80/udp
sudo ufw allow 8443/tcp
sudo ufw allow 8443/udp
sudo ufw allow 443/tcp
sudo ufw allow 443/udp
sudo ufw allow 31384/tcp
sudo ufw allow 31384/udp

sudo ufw status verbose
```

输出以下内容表示成功

<img width="1202" height="1128" alt="image" src="https://github.com/user-attachments/assets/ff97d651-7ae3-47c8-994a-9b461a7f662d" />

--

#### 4. 安装3x-ui

接下来需要严格按照以下内容执行，完成安装
1. 命令行输入 `x-bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)`
2. 第一个需要输入的地方，先输入 y 回车，然后输入8443 回车，这里是在设置3xui的网页端口

<img width="1984" height="262" alt="image" src="https://github.com/user-attachments/assets/f39a0a07-d8b5-49a1-9cc0-6487c180e195" />

---

3. 接下来连续三个需要输入的地方，都直接 回车，不要输入任何信息，这里实在设置证书签名的验证端口

<img width="1964" height="730" alt="image" src="https://github.com/user-attachments/assets/6b511d9b-1fea-4e37-a2ae-390b1e3e30b8" />

---

4. 稍等片刻，看到如下信息表示安装完成，将3xui的网页地址、用户名和密码拷贝出来。

<img width="2099" height="903" alt="image" src="https://github.com/user-attachments/assets/34d17db3-8b27-4d61-a5a6-5c822b7a0483" />

---

### Step 4：在 3x-ui 中配置 VLESS-Reality 入站节点

浏览器中访问3xui的网页地址，如果访问失败，先检查是不是开启了VPN。输入用户名密码，登录系统。

**1. 登录面板**
打开浏览器，访问 `http://你的服务器IP:面板端口`（例如 `http://198.51.100.1:54321`）。输入刚才设置的账号和密码。

**2. 创建入站规则**
在左侧菜单点击 **入站列表 (Inbounds)**，然后点击右上角的 **添加入站 (Add Inbound)**。按照以下参数进行精确配置：

<img width="3150" height="972" alt="image" src="https://github.com/user-attachments/assets/1111df2c-733b-4c20-bb37-508b40226144" />

按照下图配置

<img width="3200" height="4722" alt="FireShot Capture 003 - 192 204 46 253 – 入站列表 -  192 204 46 253" src="https://github.com/user-attachments/assets/218bc20f-645c-483f-bd53-c0c069740363" />


* **备注 (Remark)**：随意填写，例如 `AI-Dedicated-Node`
* **协议 (Protocol)**：选择 `vless`
* **监听 IP (Listen IP)**：留空即可
* **端口 (Port)**：填写 `443`
* **传输协议 (Network)**：选择 `tcp`
* **安全性 (Security)**：选择 `reality`

**3. 配置 Reality 细节**
在弹窗下方的 Reality 专属设置区中操作：

* **uTLS**：选择 `chrome`
* **目标网站 (Dest)**：填写 `www.yahoo.com:443` 或 `www.microsoft.com:443`（选择一个未被墙的海外高权重网站）。
* **SNI**：填写与目标网站一致的域名，例如 `www.yahoo.com`。
* **私钥/公钥**：点击旁边的 **Get New Cert** 按钮，系统会自动生成一对全新的 Keys。
* **ShortIds**：点击后面的 `+` 号生成一个随机字符串。

点击 **添加 (Add)** 保存。

**4. 获取节点链接**
在面板入站列表，点击刚刚创建的节点左侧的**操作 (二维码图标)**，选择 **复制链接 (Copy Link)**。这会生成一串 `vless://...` 开头的导入链接。

<img width="3153" height="1682" alt="image" src="https://github.com/user-attachments/assets/07ff9dc3-b57a-4d37-ba51-d357b0909c43" />


---

### Step 5：在 3x-ui 中配置 ISP出站节点和路由规则

1. 在Xray设置-出站规则中，点击“添加出站规则”按钮。

<img width="1874" height="925" alt="image" src="https://github.com/user-attachments/assets/2d5c8ca5-00f0-497a-8792-65e9c7c75231" />

---

2. 按照如下截图将ProxySeller提供的信息填入

<img width="983" height="1052" alt="image" src="https://github.com/user-attachments/assets/cd2ba7dc-c855-4c65-af14-b8519a807086" />

---

3. 切换到路由规则，点击“添加规则”按钮，添加一条规则：所有流量都通过ProxySeller的代理发出。

<img width="988" height="1285" alt="image" src="https://github.com/user-attachments/assets/6a8b58a0-15bf-4916-90dc-408895453ae9" />

---

4. 至此3x-ui配置完毕。


### Step 6：使用 Throne 客户端连接节点

Throne 是一款跨平台的 GUI 代理客户端（由 Nekoray 分支演进而来的高性能工具，由 Sing-box 提供核心支持），UI 现代且资源占用极低。

**1. 下载 Throne**
前往 Throne 的 GitHub 官方发布页：`https://github.com/throneproj/Throne/releases`
根据你的操作系统下载最新版安装包（例如 Windows 下载 `.exe` 或 `.zip`，Ubuntu 桌面版下载 `.deb`）。

**2. 导入节点**

* 打开 Throne 客户端。
* 确保你刚刚在Step 4中创建的 `vless://` 链接在系统剪贴板中（也就是刚刚Ctrl+C过）。
* 在客户端主界面选择`应用程序-添加来自剪贴板的配置档`。
* 右键点击新出现的配置，选择`启动`

<img width="1290" height="818" alt="image" src="https://github.com/user-attachments/assets/e07abbcd-841d-429e-aa0f-4baae186650e" />


**3. 启动系统代理**

* 勾选节点左侧的选框选中该节点。
* 按回车键，或右键选择 **启动 (Start)**。
* 在客户端顶部菜单栏，勾选 **TUN 模式**。
* **请注意，如果你在使用Antigravity、Claude、CodexApp等开发工具，必须开启TUN模式**

<img width="1586" height="703" alt="image" src="https://github.com/user-attachments/assets/1b5d9dfc-4ae8-4c2e-b8b6-a7fd8bbb7a94" />


完成上述步骤后，你的网络环境就已经被 ProxySeller 的纯净 IP 完全覆盖。现在打开 Claude 或 Gemini，你会发现区域限制已被彻底解除。

---

### Step 6: 让Throne绕过大陆ip和域名

* 打开Throne客户端。
* 点击“路由”-“下载配置档”-“Bypass_China”
<img width="1085" height="654" alt="image" src="https://github.com/user-attachments/assets/9cda0b13-77da-4937-b065-f1f222230e3b" />
* 稍等片刻，再次点击“路由”，选择“Bypass China”即可实现，访问大陆网址时，不走代理；访问海外网址和ip时，走代理
  <img width="876" height="545" alt="image" src="https://github.com/user-attachments/assets/9c00cc3f-9641-443a-b1ff-4b4318d9b574" />

