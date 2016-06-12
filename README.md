# wiki
## 开发环境配置

## Android编码风格
本文参考[Hawstein翻译的Google Java编程风格指南](http://www.hawstein.com/posts/google-java-style.html)、[Android开源项目-编码风格规范-Code Style Guidelines for Contributors](http://blog.sina.com.cn/s/blog_48d491300100zwzg.html#use-todo-comments)、[最佳实践之Android代码规范](http://www.androidchina.net/2141.html)
### 命名规范

#### 文件名命名规范
源文件以其最顶层的类名来命名，大小写敏感，文件扩展名为.java
全部小写，采用下划线命名法。

activity layout： ```activity_{名称}``` 例如：```activity_main.xml | activity_shopping.xml```

fragment layout： ```fragment_{名称}``` 例如：```fragment_main.xml | fragment_shopping.xml```

Dialog layout： ```dialog_{名称}``` 例如：```dialog_loading.xml```

adapter的子布局： ```item_{名称}``` 例如：```item_order.xml```

widget layout： ```widget_{名称}``` 例如：```widget_shopping_detail.xml```

包含项布局命名： ```include_{名称}``` 例如：```include_head.xml```

#### 资源ID命名规范
命名模式为：```{view缩写}_{view的逻辑名称}```，如：

顾客管理CRM模块布局 ```LinearLayout``` 的布局id –> ```ll_content```

模块简称为qz的 ```ImageView``` 的布局id –> ```iv_photo```

常见控件View与其缩写对照参考表如下：

| 控件              | 缩写          |
| ----------------- |:-------------:|
| LinearLayout      | ll            |
| Relativelayout    | rl            |
| FrameLayout       | fl            |
| GridLayout        | gl            |
| TextView          | tv            |
| ImageView         | iv            |
| ProgressBar       | proBar        |
| RadioButton       | rb            |
| RecyclerView      | rv            |
| ScrollView        | sv            |
| WebView           | wv            |

#### Drawable文件命名

图标命名：```ic_{名称}``` 例如：```ic_app.png```

背景图片命名： ```bg_{名称}```或者```background_{名称}``` 例如：```bg_navbar_highlight_normal.9.png``` | ```background_highlight.xml```  | ```bg_highlight.xml``` 

按钮命名：``` btn_{名称}``` 例如：```btn_login_normal.9.png``` | ```btn_login_normal.xml```

背景选择器Selector文件命名：```{缩写}_{名称}_selector``` 例如：```btn_login_normal_selector.xml```

按钮checkbox图片命名：```checkbox_{名称}``` 例如：```checkbox_cart_true.png```

其他图片命名：```icon_{名称}``` 例如：```icon_blue_circle.png```

#### 包命名规范
采用反域名命名规则，包名全部小写，连续的单词只是简单地连接起来，不使用下划线，一级包名为com，二级包名为xxx（可以是公司域名或者个人命名），三级包名根据应用进行命名，四级包名为模块名或层级名。
如：````com.zxtcode.activity````

#### 类名规范
以大驼峰式命名法(UpperCamelCase)风格编写。

每个单词的第一个字母都大写 如:```XmlHttpRequest```

类名通常是名词或名词短语，接口名称有时可能是形容词或形容词短语。现在还没有特定的规则或行之有效的约定来命名注解类型。

测试类的命名以它要测试的类的名称开始，以Test结束。例如，HashTest或HashIntegrationTest。

#### 方法名与变量名规范
以小驼峰式命名法(lowerCamelCase)风格编写。

除了第一个单词，每个单词的第一个字母都大写 如:```xmlHttpRequest```

静态成员变量用s开头。例如：
```java 
private static String sName;
```
除了Model类的私有成员变量以外私有成员变量用m开头。例如：
```java 
private String mName;
```
Model类的私有成员变量不加前缀。例如：
```java 
private String name;
```

#### 大括号问题
将大括号与起始语句放在同一行
```java
if (hasSomething()) {
 
} else {
 
}
```
#### 空格问题
if else | while | 运算符两端 等后面需用空格隔开。例如：

规范的编写方式：
```java
if (hasSomething()) {
 
} else {
 
}
 
for (int i = 0; i < 10; i++) {
 
}
```

不规范的编写方式：
```java
if(hasSomething()){
 
}else{
 
}
 
for(int i=0; i<10;i++){
 
}
```

#### 方法参数
1. 当方法参数数量过多时，需进行换行处理。
2. 尽量不要让方法参数超过五个，超过五个以上可以考虑用一个类来封装。
3. 除非只有一个参数，尽量不要使用boolean作为方法参数
4. 如果需要传的参数是Android的资源文件ID，那么需要加上注解。
Drawable使用```@DrawableRes```，Color使用```@ColorRes```，Dimension使用```@DimenRes```，String使用```@StringRes```。
