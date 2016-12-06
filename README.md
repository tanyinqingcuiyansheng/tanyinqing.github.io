
text = '# 大标题 ## 第二号 ... ' 
md = unicode(text, 'utf-8') 
markdown.markdown(md).encode('utf-8')

# tanyinqing.github.io
```
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">

http://www.bejson.com/  标准的json格式网站


    唐山燃气工程的项目思路
首先有一个登录的页面实现了登录的功能。在登录页面实现了拷贝数据库的操作。在登录页面实现了拷贝数据库
的操作，和修改ip地址的功能。以及登陆功能的实现。
    实现访问网络方法是可以写一个模拟数据替代下载的数据，访问网址，只要写一个能够访问通模拟网址就行
	了。
主页面他实现了向各个页面的跳转。
   登录页面，在2个按钮点击是，增加了对ip是否为空的判断。
   上传数据页面，上传数据时上传日志。但是日志的组建是在主页面的主导器中完成的。
   任务记录的详情，1：显示已经上传的数据从任务记录跳转进入：2：显示驳回的数据，从主页进入。


燃气系统服务器的网址
http://210.56.209.87:90/Interface/Login.aspx

临时配置数据
ServiceApplication.mPrefUtil.putSetting(Constant.AnJianZhuangKuangId,"");

if ("SecurityItem".equals(ServiceApplication.mPrefUtil.getStrSetting(Constant.SecurityItem))){
   
}else {
   
}

String tan=ServiceApplication.mPrefUtil.getStrSetting(Constant.SecurityItem);

增加友情提示的弹出框
 if (json!=null){
                    parse(json, dataListener);
                }else {
                    Toast.makeText(mContext,"返回的数据为空",Toast.LENGTH_SHORT).show();
                }

判断当前网络是否连接
if(NetUtil.getConnectedType(this)!=(-1)){//判断网络是否连接
        
    }else {
        Toast.makeText(this,"当前网络未连接",Toast.LENGTH_SHORT).show();
    }


异常分析
com.google.gson.JsonSyntaxException: java.lang.IllegalStateException: Expected a string but was 
BEGIN_OBJECT at line 1 column 3
  因为里面是一个大括号，并且又有属性，所以必须要定义对象来取值。

现在时间的获取
        Calendar calendar=Calendar.getInstance();
        Date data=calendar.getTime();
        SimpleDateFormat format=new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        String time=format.format(data);


返回的数据  这个数据data内的数据必须定义对象来解析
    "data": [
        {
            "IT_Number": "P20161118001-000001-0001"
        }
    ],
    "limit": "1",
    "msg": "查询成功!",
    "success": "true"
}



数据的解析模板代码
 public TaskListAdapter getGoodsAdapter() {
        JSONObject jsonObject;
        List<TaskListEntity> list=new ArrayList<>();
        Type type = new TypeToken<List<TaskListEntity>>() {
        }.getType();
        try {
            jsonObject = new JSONObject(dataAppUtil.TaskListData);
            if ("true".equals(jsonObject.getString("success"))) {
                Gson gson = new Gson();
                T obj = gson.fromJson(jsonObject.getString("data"), type);
                list =(List<TaskListEntity>)obj;
            }
        } catch (JSONException e) {
            e.printStackTrace();
        }
         mGoodsAdapter.appendToListAndClear(list);
        return mGoodsAdapter;
    }

	运用本地数据测试数据和方法的正确性  不依赖端口  网络数据测试的方法
  public void BoHuiShuJu(final DataListener<List<BoHuiShuJu>> dataListener) {
        RequestParams params = new RequestParams();
        post(CeShiShuJuUrl, params, new IRequestListener() {
            public void onSuccess(String json) {
                json=dataAppUtil.BoHuiShuJu;
                Type type = new TypeToken<List<BoHuiShuJu>>() {
                }.getType();
                parse(json, type, dataListener);
            }
            @Override
            public void onFailed() {
                dataListener.onFailed();
            }
        });
}

网络接口数据
 下载数据的接口 张雪的服务器   
 http://192.168.10.160:90/Interface/AppInterfaceDownLoad.ashx?U_Id=1
 下载数据的接口 87的服务器  
 http://210.56.209.87:90/Interface/AppInterfaceDownLoad.ashx?U_Id=1
 驳回的数据
 http://210.56.209.87:90/Interface/AppInterfaceDownLoad.ashx?U_Id=1



http://210.56.209.87:90/Interface/AppMonthTest.ashx?U_Id=1

android log4j日志管理的使用  
http://www.cnblogs.com/minyc/p/myc201606081439.html

App

b)	第二次安检入户安检时，默认有隐患的安检项为红色，隐患项前打钩，第三次安检入户安检时，默认有隐患
的安检项为红色，已整改的为绿色，隐患项前打钩

3、	任务列表
a)	任务列表以最小单位(房号)显示已完成的任务，显示当天已完成数量  数量以上传的数量为准
4、	主页加驳回数据修改


SQL语句
select SP_id from Task_entity group by sp_id --计划分组
--根据计划查询全部 
select * from Task_entity   where SP_Id=13  
-- 根据小区分组 
select RenWuId from Task_entity where SP_Id=13 group by XiaoQuId 
--
select * from Task_entity a ,TaskListEntity b where a.XiaoQuId=Id and a.SP_Id=13 and a.XiaoQuId=1




{"data":[{"limit":0,"msg":"接收失败!","success":"false"}]}

http://www.romzj.com/rom/25138.htm  乐蛙rom之家
搜索技巧
关键词 string java  则String相关的方法都出来了 

查询文档的网址
http://210.56.209.66:90/Interface/AppInterfaceDownLoad.ashx?U_Id=2


数据库数据的筛选
select * from Task_entity   where address2="益民园101" and address3=1 and address4=102 and 
AnJianCiShu="2次" and LeiBie=0

select * from Task_entity   where SP_Id="P20161205251" 
创建数据库的操作
创建网址的列表
create table BaseUrl (id INTEGER primary key,[BaseUrl] text);
创建日志的列表
create table RiZhi (id INTEGER primary key autoincrement,[U_Id] text,[Date] text,[IT_Number] 
text,[Content] text);
创建多个小区的列表
create table TaskListEntity (id INTEGER primary key autoincrement,[SP_Id] text NOT NULL,[XiaoQuId] 
text NOT NULL, name text not null , state text ,operation text,time text,[LouHaoList] 
VARCHAR(50),[LeiBie] VARCHAR(50),[UserId] VARCHAR(50));
创建多个安检项的列表
create table SecurityItemEntity (id text primary key,content text,RectificationGrade text);
创建多个安检状况的列表
create table SecurityStatus (id INTEGER primary key autoincrement,RenWuId text,IT_Number 
text,AnJianXiangId text,AnJianMiaoShu text,AnJianZhaoPian text);
创建多个住户的列表
create table Task_entity ([RenWuId] INTEGER PRIMARY KEY autoincrement,[SP_Id] text NOT 
NULL,[YonghuId] text NOT NULL,[DisNumber] text NOT NULL,[XiaoQuId] text NOT NULL,[AnJianXiangId] 
VARCHAR(200),[AnJianZhuangKuangId] VARCHAR(200),[state] TEXT,[RectificationGrade] 
TEXT,[AnJianZhuangTai] text,[operation] VARCHAR(50),[address2] VARCHAR(50),[address3] 
VARCHAR(50),[address4] VARCHAR(50),[category] VARCHAR(50),[LeiBie] 
VARCHAR(50),[DanTiao] VARCHAR(50),[StopTime] VARCHAR(50),[IT_Number] VARCHAR(50),[BoHuiLiYou] 
VARCHAR(50),[UserId] VARCHAR(50),[AnJianCiShu] VARCHAR(50),[IT_Reject] VARCHAR(50),[IT_State] text 
DEFAULT '0',[AD_Name] text DEFAULT '',[AD_Phone] text DEFAULT '');


正确的SQ语句
create table MyBaodianFavorite ([Id] INTEGER DEFAULT '0' PRIMARY KEY AUTOINCREMENT,[NewsId] 
INTEGER NOT NULL,[AppType] VARCHAR(50) NOT NULL,[ImageUrl] VARCHAR(50),[Introduction] TEXT NOT 
NULL,[Title] VARCHAR(50) NOT NULL,[Author] VARCHAR(50) NOT NULL,[PubDate] VARCHAR(50) NOT NULL)

分组  就是显示字段下的全部数据
select address2,address3 from Task_entity where SP_Id=13 and XiaoQuId=1 group by address3 
查询分组的所有数据
select * from Task_entity where SP_Id=15 and XiaoQuId=17 group by address2 
分页显示数据
select address2,address3 from Task_entity where SP_Id=13 and XiaoQuId=1 group by address3 limit 1

select * from Task_entity limit 3,10

cursor=db.query(TableName, null,null,null,null,null,null,"5,9");//"5,9",第6行开始,返回9行数据

 db.query(TABLE, new String[]{NUM,MODE}, null, null, null, null, null, offset+","+limit);

Cursor cursor = db.query("Task_entity", new String[] { 
"RenWuId","SP_Id","state","category","operation","AnJianXiangId","AnJianZhuangKuangId","address2",
"address3","address4",}, "XiaoQuId=? and SP_Id=? and LeiBie=? and address2=? and address3=?", new 
String[] {XiaoQuId,SP_Id,LeiBie,address2,address3}, null, null,null, "0"+","+"4");

primary key 主键的值是唯一的不重复的  autoincrement 自增长

9.3.3 数据库查询详解
使用完全结构化的 SQL 查询，可以非常容易地为指定数据创建过滤器，并从数据库返回符合过滤
条件的子集全。有多个重载的 SQLiteDatabase.query()方法，可用来从数据库查询数据。其定义如下：
public Cursor query(String table, String[] columns,
String selection,
String[] selectionArgs,
String groupBy,
String having,
String orderBy,
String limit)
前两个参数分别是要查询的表名以及要返回的每行记录的列名。其它的参数定义我们怎样缩小查询
结果的范围

and与or分开查询条件
Cursor cursor = db.query("Task_entity", new String[] 
{"RectificationGrade","IT_Number","AnJianZhuangTai","XiaoQuId","address2","address3","address4","s
tate","YonghuId","DisNumber","AnJianZhuangKuangId","RenWuId","AnJianXiangId","LeiBie","DanTiao"}, 
"XiaoQuId=? and  ( LeiBie=? or LeiBie=? or LeiBie=? or LeiBie=? ) ", new String[] 
{"236","3","2","4","0"}, null, null, null);


/**

*
 table="表命", 

*
 columns="要查询的列名", 

*
 selection="查询 条件", 

*
 selectionArgs="条件中用了占位符的参数", 

*
 groupBy="数据分组", 

*
 having="分组后的条件", 

*
 orderBy="排序方式", 

*
 limit="分页查询";  

**/


项目安排


复调整变动我就没办法预测了
耿书山 2016/11/9 星期三 上午 9:43:22
任务下载：支持单任务或多任务下载，下载过程中提示下载进度 

。 

耿书山 2016/11/9 星期三 上午 9:43:49
1、个人信息管理：提供用户信息、密码修改；
2、服务器参数管理：配置服务器连接地址、端口
3、数据存储管理：配置数据存储周期
4、软件更新：系统自动提示更新
耿书山 2016/11/9 星期三 上午 9:44:18
还得加日志，到时候我们这边提供个接口，他得把操作日志传回来
上午 9:44:44
耿书山 2016/11/9 星期三 上午 9:44:44
我安检过程中的信息，一定要有详情，无论上次数据，还是任务列表
耿书山 2016/11/9 星期三 上午 9:45:07
对了，他那边还有一个问题，如果我二次安检的时候，我必须带第一次安检的隐患项，第一次的隐患项默认打勾
，且隐患项好像用红色表示，第三次安检时，第二次安检的隐患项默认打钩，还存在隐患的继续用红色表示，已
经整改过的用绿色表示






关键文件夹
D:\压缩文件夹

唐山燃气工程地址连接
http://192.168.1.187/GarverInterface/Interface/AppInterface.asmx



一切都为学习服务，请劳逸结合


数据库的建立模式
1 首先建立新的数据库SecurityCheck
2 右键New Table，建立新的数据库表。


Android压缩图片到100K以下并保持不失真的高效方法
 http://www.360doc.com/content/14/0428/17/11800748_372972179.shtml
 android 比较靠谱的图片压缩
 http://104zz.iteye.com/blog/1694762

我做了个项目管理的系统
http://210.56.209.87/zentao/user-login-L3plbnRhby8=.html
tanyq




微信支付
req.appId="wx405f674449bed855";
req.partnerId="1385752402";

//req.appId = "wxf8b4f85f3a794e77";  // 测试用appId							
							/*req.appId			= json.getString("appid");
							req.partnerId		= json.getString("partnerid");*/
							req.appId			= "wx405f674449bed855";
							req.partnerId		= "1385752402";
							req.prepayId		= json.getString("prepayid");
							req.nonceStr		= json.getString("noncestr");
							req.timeStamp		= json.getString("timestamp");
							req.packageValue	= json.getString("package");
							req.sign			= json.getString("sign");
							req.extData			= "app data"; // optional

搜索地址
D:\studiospace\MarsBabyShop
D:\workspace\HeartMark



心衰管理数据模式
POST
one
http://api.hf.ixinzang.com/article/getXSArticleList?ht=%7B%22ApplicationID%22%3A10%2C%22DeviceID%2
2%3A2%2C%22ArticleCategoryID%22%3A6%2C%22PageIndex%22%3A1%2C%22PageSize%22%3A10%7D


two
http://api.hf.ixinzang.com/article/getXSArticleList?ht=%7B%22ApplicationID%22%3A10%2C%22DeviceID%2
2%3A2%2C%22ArticleCategoryID%22%3A7%2C%22PageIndex%22%3A1%2C%22PageSize%22%3A10%7D

three
http://api.hf.ixinzang.com/article/getXSArticleList?ht=%7B%22ApplicationID%22%3A10%2C%22DeviceID%2
2%3A2%2C%22ArticleCategoryID%22%3A8%2C%22PageIndex%22%3A1%2C%22PageSize%22%3A10%7D

详情页面：
POST
one 
http://api.hf.ixinzang.com/user/userLively?ht=%7B%22DeviceID%22%3A2%2C%22ApplicationID%22%3A10%2C%
22UserID%22%3A%22474546%22%2C%22LoginToken%22%3A%22f4ecb567-a696-4727-ae92-9695103cce47%22%2C%22Cu
rrentDate%22%3A%222016-10-11%22%7D


two
http://api.hf.ixinzang.com/article/getXSArticleDetail?ht=%7B%22ApplicationID%22%3A10%2C%22DeviceID
%22%3A2%2C%22UserID%22%3A%22474546%22%2C%22LoginToken%22%3A%22f4ecb567-a696-4727-ae92-9695103cce47
%22%2C%22ArticleID%22%3A2414%7D

three
http://api.ixinzang.com/user/getMyDoctorRelationHistory?ht=%7B%22UserID%22%3A%22474546%22%2C%22Dev
iceID%22%3A%222%22%2C%22ApplicationID%22%3A%2210%22%2C%22LoginToken%22%3A%22f4ecb567-a696-4727-ae9
2-9695103cce47%22%7D


Chrome浏览器
打开新的标签页，并跳转到该标签页Ctrl + t	

java.lang.NoClassDefFoundError: javaapplication6.Tan
打包文件 MANIFEST.MF 功能详解

燃气安检的思路
1 关于数据的下载 
下载时加入一个参数，用来定义数据传输的数目，如果解析后数据的数目一致，就保存到数据库，如果不一致，
就让客户重新下载。

2 集成开发环境的使用
1利用exlipse生成jar包
2如何利用studio生成库文件

source tree 这个软件时gitbook的编译和上传软件


数据库这本书的网址  http://forta.com/books/0672336073/

订单加密的3个元素：付款的金额，订单的描述信息，订单号（必须唯一）。

 安卓版本测试，测试手机红米NOTE 3，测试环境WIFI   
1、    搜索框显示“搜索邻优商品/店铺”，是无法搜索店铺的，建议改为“输入商品名字”。   
    
2、	10元起送的标准需要修改下，现在是必须超过10元，才能结算，刚好10元是无法结算的，我们希望改为达到
10元就可以配送，如10元整。另外，这个配送金额在哪设置？如何设置？比如我们想把配送金额改为15元。   
3、	在购物车里的配送通知，做的挺好的。同样的问题，我们在哪里可以修改显示的内容，以及如何控制在什么
时候显示配送通知？   
4、	目前还无法实现网上支付（支付宝、微信）。   
5、	用户换手机登录后，相关信息丢失，如“配送地址”。   
6、	用户昵称：建议直接显示用户的注册账号。   


英语关键字
包名 
类名 Runnable Thread
方法名


保密信息
微信
AppID：wx405f674449bed855
商户号：1385752402





创建订单的链接
http://192.168.10.192:8080/umijoyappsvr/order/createOrder.do?goodsIds=24989N1C24536N1&user.id=479&
deliveryAddress.id=449&payMethod.id=12&discountCode=fghhgfhgfh&remark=%E4%B8%8D%E7%94%A8%E9%85%8D%
E9%80%81&storeId=28&storeName=%E5%98%89%E6%9F%8F%E5%B0%8F%E5%8C%BA


/*09-18 13:31:59.153  28013-28013/? D/查看生成订单的操作﹕ 
http://211.149.169.221:8080/umijoyappsvr/order/createOrder.do   
		 *  goodsIds   24989N1C24536N1      user.id   479      deliveryAddress.id  449      
		 payMethod.id  12      remark  App测试，不用配送      discountCode        storeId  28     
		  storeName  嘉柏小区
			09-18 13:31:59.153  28013-28013/? E/post﹕ 
			http://211.149.169.221:8080/umijoyappsvr/order/createOrder.do
*/

{"data":"timestamp=2016-07-29+16%3A55%3A53&biz_content=%7B%22timeout_express%22%3A%2230m%22%2C%22p
roduct_code%22%3A%22QUICK_MSECURITY_PAY%22%2C%22total_amount%22%3A%2250.0%22%2C%22subject%22%3A%22
%E4%BC%8A%E5%88%A9+%E9%87%91%E5%85%B8+%E7%BA%AF%E7%89%9B%E5%A5%B6+250ml%2F%E7%9B%92%22%2C%22out_tr
ade_no%22%3A%221412462532%22%7D&sign_type=RSA&charset=utf-8&method=alipay.trade.app.pay&app_id=201
6082301791132&version=1.0&sign=er6RXHwdn4oTIIXzVHVmWe65%2Faybb1hedFJU1bOJ%2FcZ3fos3NyISXkJW2axIRzi
Bbhgjson9Ld6tCEtt5NSrf3h0eTWQtXVlol9Qhp2giIgma9C5pMXqCrEksaT5yn4STRKBeK7RLF0FBWr3pZMV1FeYUUwvvMTUq
hc%2BZ%2F6%2FCpo%3D","msg":"查询成功！","success":true}

{"data":"timestamp=2016-07-29+16%3A55%3A53&biz_content=%7B%22timeout_express%22%3A%2230m%22%2C%22p
roduct_code%22%3A%22QUICK_MSECURITY_PAY%22%2C%22total_amount%22%3A%2250.0%22%2C%22subject%22%3A%22
%E4%BC%8A%E5%88%A9+%E9%87%91%E5%85%B8+%E7%BA%AF%E7%89%9B%E5%A5%B6+250ml%2F%E7%9B%92%22%2C%22out_tr
ade_no%22%3A%221412462532%22%7D&sign_type=RSA&charset=utf-8&method=alipay.trade.app.pay&app_id=201
6082301791132&version=1.0&sign=er6RXHwdn4oTIIXzVHVmWe65%2Faybb1hedFJU1bOJ%2FcZ3fos3NyISXkJW2axIRzi
Bbhgjson9Ld6tCEtt5NSrf3h0eTWQtXVlol9Qhp2giIgma9C5pMXqCrEksaT5yn4STRKBeK7RLF0FBWr3pZMV1FeYUUwvvMTUq
hc%2BZ%2F6%2FCpo%3D","msg":"查询成功！","success":true}

生成订单的参数
  deliveryAddress.id  449      payMethod.id  12      remark  App测试，不用配送      discountCode  
        storeId  28      storeName  嘉柏小区
09-14 13:20:22.897  22479-22479/com.linyou.lifeservice E/post﹕ 
http://211.149.169.221:8080/umijoyappsvr/order/createOrder.do
09-14 13:20:24.777  22479-22479/com.linyou.lifeservice D/jack﹕ 比较sessionid  null
09-14 13:20:24.777  22479-22479/com.linyou.lifeservice I/System.out﹕ parse ----------> 
{"data":null,"msg":"生成订单成功！","success":true}



Log的过滤
点Display saved Filters view
建立一个过滤tanyinqing 就可以实现过滤有用信息了 




支付宝核心参数
  http://blog.csdn.net/twlkyao/article/details/26340685   
  

支付功能的实现
一主要配置的参数
/** 支付宝支付业务：入参app_id */
	/*app_id 客户端号 String 标识客户端。 可空 external*/
	public static final String APPID = "";
	
	/** 支付宝账户登录授权业务：入参pid值 */
	/*查询合作者身份(pid)  合作身份者id，以2088开头的16位纯数字*/
	public static final String PID = "";
	/** 支付宝账户登录授权业务：入参target_id值 这个就是支付宝公钥*/
	public static final String TARGET_ID = "";

	/** 商户私钥，pkcs8格式 */
	public static final String RSA_PRIVATE = "";


二 本文中对应的DEMO在文章底部给出。

R.layout.pay_external 第一个页面的XML文件
App支付Android集成流程详解  
https://doc.open.alipay.com/docs/doc.htm?spm=a219a.7629140.0.0.9X1RdA&treeId=204&articleId=105296&
docType=1

支付宝支付流程安排  两种 方案
第一种
先购物车里进行购买，购买之后购物车页面关闭，进入订单详情页面，在订单详情页面设置付款按钮，点击付款
按钮完成付款后，订单详情页面关闭，回到商品列表页面。这种类似淘宝
第二种
先购物车里进行购买，购买之后购物车页面关闭，进入订单详情页面，在订单详情页面设置付款按钮，点击付款
按钮完成付款后，订单详情页面关闭，跳转到我的订单列表页面，顾客可以看到自己购物订单

以上两种方案 看你们考虑哪一种流程 考虑不到的地方，也希望你们提出自己的想法

得到一个随机数
Random r = new Random();
 r.nextInt();
截取字符串的前15位
key = key.substring(0, 15);



https://b.alipay.com/signing/productDetail.htm?productId=I1011000290000001002  APP支付说明

eclipse中设置文件的编码格式为utf-8
http://ryxxlong.iteye.com/blog/788469

* [1.studio](#1)
<h6 id="1">1.studio</h6>




ActivityManager am = (ActivityManager) getSystemService(ACTIVITY_SERVICE);
am.killBackgroundProcesses(info.getPackname());//杀死进程

眼睛有血丝怎么办 http://jingyan.baidu.com/article/6b97984d77ffd11ca2b0bf2d.html
 																				 
                                                                                                  
邻优网配送端
1 客户端生成新订单后，配送端有推送信息，但看不到新订单。
2 还是会出现提交订单失败的情况，例如用户ID479，在订单提交失败后，所有的订单都无法正常访问。

     
                                                                                                  
耿爷，跟您回报下邻优网配送端进度。
	接口写完了，但有一些Bug，我已经跟郭登晋反应了，他最近正在写另外一个项目，说抽时间改。
	客户端我也做了一个初步版本出来，已经发给客户了，他说测试后给我反馈。

	耿爷，我有个申请，不知道是否允许？我想利用做Android项目的间隙，学学集成，这样在时间允许的情况
	下，我还能多为公司做一些事！不知道耿爷的意见。


/******************************成员变量**************************/
						生活配送端web后端接口
一登录页面
1.1	成功登陆返回用户资料
二注册页面	
2.1	获取手机验证码
2.2	用户注册
三个人中心页面	 UserCenterActivity
3.1 注销登录

四修改资料页面 UserInfoActivity
4.1 上传头像

五修改密码页面 ModifyPassWordActivity

六 Bug的处理
6.1 清单文件出现莫名的错误：可编译，看提示，主要是R文件出现错误导致。然后再clean，实在不行在
重启文件。
6.2 activity布局文件无法加载 最后检查原因是里面有一个自定义控件，这个自定义控件的路径是错误的。
6.3 弹出框一加载就页面崩溃，最后检查是弹出框引用的布局文件中包含自定义的控件，但路径是错误的。


/***************************************************************/



2美工设计一个UI，我设计


账号377198042@qq.com  密码：guodengjin0612
极光推送
AppKey： 0cc59ab8b965cb5db8233b5d
Master Secret： ?  e922fce4ab2539c4846d8518  重置 Master Secret
创建日期： 2016-06-30 13:18:31
最后修改时间： 2016-06-30 13:18:31


android.os.Vibrator 振动
android.app.NotificationManager  

Xutils 这个文件讲的就是这个框架的应用，有错误，自己记得看
 
 小米刷机工具地址
E:\cancro_images_V7.3.3.0.MXDCNDD_20160419.0000.19_6.0_cn_be9702a353\cancro_images_V7.3.3.0.MXDCND
D
_20160419.0000.19_6.0_cn

适配的图片一般在xhdpi和xxhdpi两种高分辨率中。
	


小米的图片的文件夹在DCIM这个文件夹中

思维导图软件 D:\tanyinqing\软件\思维导图软件

Android 源码库的学习

D:\安卓程序源码学习\安卓2014.04.30新增500源码\安卓2014.04.30新增500源码
\Android应用源码之[安卓开源
]GuideViewDemo(超炫丽用户引导)

D:\安卓程序源码学习\安卓2014.04.30新增500源码\安卓2014.04.30新增500源码
\Android应用源码之漂亮的自定
义圆形进
度
条

D:\安卓程序源码学习\AndroidApe.com-安卓程序源码服务专家起始
-1122\AndroidApe.com-安卓程序源码服务专
家起始
-1122\生活相关\Android 带手势划动功能的日历源码\Android 带手势划动功能
的日历源码\Android 带手势划动
功能的日
历
源码

显示商品类别   
http://211.149.169.221/app_res/category_img/frozen_food.png
http://211.149.169.221:8080/umijoyappsvr/goods/findServiceTypeByDistric
t.do?storeId=10

ctrl+滚动轮 动态切换大小

动态的显示店铺和商品类别的实现
思路

重新定义一个类
这个类包含三个方面的内容

商品类别的cate_id值
商品类别的名称
商品类别的图片

返回时返回一个有序的集合

保存地址信息是把他的类别信息同步的保存到配置信息中

执行思路
1定义这个类
2定义adapter的时候,采用对象集合为数据源的格式

借鉴的思路
区域信息的保存
把区域对象的集合作为adapter的数据，展示的是对象中的某个属性
点击条目时保持数据对象


   


数据库查询
where goods_id =38433

网站数据库相关信息
地址：http://www.umijoy.com/phpmyadmin----/
账号：root
密码：220170


C:\Users\Administrator\Downloads  数据默认下载地址

首先cookie是空的
先访问网络
获得session  保存到本地   比较sessionid肯定是空的

session不为空  在session中加入特定元素  加入到请求头中去
在访问网络是将请求头带到服务器


```  
