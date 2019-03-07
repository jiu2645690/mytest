# 开发工具 IntelliJ IDEA
# 缓存工具 redis
# 数据库 mysql
# 服务器部署说明：
 ##开发配置
   -1.安装 开发工具 IntelliJ IDEA  x64
   -2.打开 IntelliJ IDEA  x64，点击右上角file=》open  找到项目所在位置。选择项目所在文件夹，点击OK 
   -3.安装MySQL，（http://www.pc6.com/softview/SoftView_28585.html 下载 按照图片说明，进行安装。并设置好 数据库账号 密码
   -4.在目录中找到 src=》resource 下的 application.yml。查看datasource 下的url 配置的。
   dbc:mysql://101.37.124.77:3306/xiaoshitest（101.37.124.77 ：数据库服务器的IP（即：第二步 数据安装） 本机127.0.0.1，3306 mysql 的端口，      xiaoshitest 数据库名称）
     username: （第二部设置的数据库账号）
     password: （第二部设置的数据库密码）
    -5.启动redis-server 中 redis-server.exe 看到启动 dos启动框，则说明启动，如果闪一下，没有启动
    可以通过dos命令：1 打开dos窗口，定位到redis-sever文件下，输入 redis-server.exe redis.windows.conf
     -6.在 IntelliJ IDEA  x64启动。 
     -7.打包 打开dos命令窗口，定位到 项目目录， 输入 mvn clean package -DskipTests。出现：bulid sucess 则表示完成。
       打开 目录下target 文件夹 找到 order-0.0.1-SNAPSHOT.jar 。到此打包结束。
      -8 发布到服务器. 将打包文件上传到服务器。 打开dos命令窗口 定位 jar包所在文件， 输入命令： java -jar order-0.0.1-SNAPSHOT.jar输入回车
        则项目启动。
      -9，反向代理设置 
    上传 nginx 到服务器。
      在nginx 文件下 找到 /conf/nginx.conf
   在 http server
   配置
     listen       80;//端口   http 访问的端口
        server_name  www.liwi.vip  http文件域名
    在HTTPS server （小程序端使用）
    server_name www.liwi.vip  //配置 https 的域名
    ssl_certificate        C:/ssl/215053788620195.pem //证书文件
    ssl_certificate_key  C:/ssl/215053788620195.key;  //证书加密文件
  配置完成后启动 nginx.exe 即可
# 目录结构
  ## mian  //项目主体程序
   ### config  //项目配置文件
    #### BuketConfig  //s3 存储相关配置
    #### DataSourceConfig  //数据库相关配置
    #### DefaultInfoConfig  //默认配置
    #### MealTimeConfig  // 送餐时间配置
    #### MessageConfig   //短信发送相关配置 （如果 发送不成功，或者未启动 发送短信功能，系统将发送默认验证码 1234）
    #### OrderConfig  //订单相关配置
    #### WechartConfig   //微信相关配置
    #### ApplicationConfig   // 后台系统审核配置， 可以配置未自动审核
   ### constant 
    #### ApplicationCode   //店铺审核状态枚举类
    #### LogCode   //错误日志枚举
    #### OrderCode   //错误枚举
    #### OrderSateCode   //订单状态枚举
    #### RedisConstant   //redis数据库过期配置
    #### ShoppingCartLineItemCode   //购物车行失效类型枚举
    #### ShoppingCartLineItemStateCode   //购物车行状态枚举
    #### UserTypeCode   //用户类型枚举
    #### WalletCode   //钱包流水类型枚举
### dao 数据访问层     
### exception  异常机制
### service  业务逻辑层
### service  pojo
    #### dto //返回实体类 
    #### entity  //数据库实体
    #### form //上传的表单
    #### model //商用返回的实体 
    #### Task //定时计划任务任务
### util   工具类
    #### DateUtil   //日期类工具
    #### EncryptDecryptByKeyUtil   //加密解密工具类
    #### EnumerationUtil   //枚举类工具
    #### FileNameUtils   //文件相关工具
    #### JsonUtil   //json 处理相关工具
    #### LoginUtil   //登陆验证工具类
    #### LogUtil   //日志工具类
    #### OperatingSettingUtil   //营运设置相关工具类
    #### PageUtil   //分页工具类
    #### ParameterCalibrationUtil   //参数校验工具类
    #### PictureUtils   //图片上传到 s3 工具类
    #### RandomSumUtil   //随机数生成工具类
    #### RedisUtil   //Redis工具类
    #### TokenUtil   //token工具类
    #### UUIDUtils   //UUID生成工具类
### web   
  #### aop   //
  #### controller   //控制器
  #### application   //系统的配置
### resources
  #### mapper //数据库访问xml
  #### resources
## test  //单元测试

