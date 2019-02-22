# 开发工具 IntelliJ IDEA
# 缓存工具 redis
# 数据库 mysql
# 服务器部署说明：
 在服务器上 安装MySQL，启动redis-sever 。启动 xxx.jar 文件
（https 小程序端会用到） 采用nginx，上传证https 证书到服务。在nginx中进行配置后。启动nginx。并指向  xxx.jar的端口。可实现http+https 两种方式访问。
# 目录结构
  ## mian  //项目主体程序
   ### config  //项目配置文件
    #### BuketConfig  //s3 存储相关配置
    #### DataSourceConfig  //数据库相关配置
    #### DefaultInfoConfig  //默认配置
    #### MealTimeConfig  // 送餐时间配置
    #### MessageConfig   //短信发送相关配置
    #### OrderConfig  //订单相关配置
    #### WechartConfig   //微信相关配置
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

