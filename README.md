# NewsClient

> 特别提示：数据来源可以使用聚合数据。具体更改自行查聚合数据API。视图适配做的聚合数据。

#### 新闻Android客户端

<hr>


## 一、需求分析

1. 要求实现体育、财经、娱乐、科技等多个新闻版块（或者自定义），并可以自由通过导航菜单切换。
2. 对每条新闻可以打开，进行阅读详细信息，包含丰富的图片和文字。
3. 对每条新闻可以进行点赞和评论。
4. 新闻数据： 如果动手能力较强，可以尝试自己动手用 PHP、JSP 等搭后台，利用Android 网络编程，或者通过网络爬虫，爬取相关的新闻素材。

------

## 二、总体设计

**1.系统需求分析**
    通过Android Studio软件尝试搭建出一个简易的新闻客户端，用户可以通过该客户端实时的查看新闻，并且有多个新闻板块可供用户选择。

**2.系统功能分析**
该新闻客户端需要完成的功能模块主要有：

- ·广告界面：刚打开APP会显示广告。

- ·登录界面：支持账号、密码登录注册，并且信息存储在SQLite数据库中。

- ·首页：新闻界面，开始加载进入会显示社会新闻一栏。

- ·侧边栏：有用户头像、信息以及各个板块新闻可供用户进行跳转。

- ·头像：可使用拍照或相册文件自动更换头像。

  

**3.设计步骤**

1. 设计加载页界面样式（广告），完成对应活动的注册和java代码的绑定。
2. 设计登录页界面样式，创建数据库并连接，完成相应的SQLite代码编写与java代码的调用。
3. 设计编写主页界面、侧边栏样式、导航栏样式。
4. 爬取相应网站新闻内容，并封装成json包并挂入服务器中。
5. Android studio中导入Gson解析包。
6. 编写Gson解析代码并解析服务器中的json包，将数据传入View中显示。
7. 设计对应java代码的点击事件，完成点击不同的列表选项展示不同的新闻板块。
8. 设置Dialog，当点击头像时，显示列表（拍照、从手机相册选择、取消）。
9. 设计从手机相册中选择图片并更换头像，编写对应java类，注册Android相应权限。

  10.设计拍照并更换头像，编写对应java类，注册Android相应权限。

------

## 三、详细设计：

**1、数据流程图**

![](https://github.com/Chien-W/NewsClient/blob/main/picture/%E6%95%B0%E6%8D%AE%E6%B5%81%E7%A8%8B%E5%9B%BE.png)      

**2、数据库概念结构设计**

![](https://github.com/Chien-W/NewsClient/blob/main/picture/%E6%95%B0%E6%8D%AE%E6%B5%81%E7%A8%8B%E5%9B%BE.png)

数据表:username为账号，password为密码。

***3、爬取数据，存储服务器***

| ***新闻名***   | ***数据名***   | ***数据格式*** | ***来源***   |
| -------------- | -------------- | -------------- | ------------ |
| ***社会新闻*** | ***Shehui***   | ***Json***     | ***服务器*** |
| ***国内新闻*** | ***Guonei***   | ***Json***     | ***服务器*** |
| ***国际新闻*** | ***Guoji***    | ***Json***     | ***服务器*** |
| ***娱乐新闻*** | ***Yule***     | ***Json***     | ***服务器*** |
| ***体育新闻*** | ***Tiyu***     | ***Json***     | ***服务器*** |
| ***科技新闻*** | ***Keji***     | ***Json***     | ***服务器*** |
| ***军事新闻*** | ***Junshi***   | ***Json***     | ***服务器*** |
| ***财经新闻*** | ***Chaijing*** | ***Json***     | ***服务器*** |
| ***时尚新闻*** | ***Shishang*** | ***Json***     | ***服务器*** |

将爬取的数据用json封包后，装入服务器中，每次APP直接读取服务器中的json包，解析后即可展示新闻。

------

功能开发记录

<hr>
V 0.1

设计头像框并可本地更换头像

导入新闻列表

设计导航栏

设计侧边栏

设计登录页面

