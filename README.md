# 孙君雅 - JAVA后端开发



## 联系方式

- 电话：15927188503
- 邮箱：1576200085@qq.com

---

## 个人信息

- 女/1997/23
- 本科/武汉纺织大学/软件工程/2015-2019
- 工作年限：3年

---

## 工作经历

### 平安壹钱包      中间件        2018 ～ 至今

#### 数据中转站

​        该系统为业务系统提供全局的缓存服务，存储大字段数据，减少业务系统间大字段数据的交互，并且在数据库出现偶尔卡顿或者短时间内不可用时对上层服务调用方无影响。

​        该系统全部有我开发，包括：系统基本get&set功能开发；使用guavacache存储变更较少的数据，减少部分网络消耗；接入redis提升数据读取速度并且作为数据库出现异常时的数据存储设备；使用activeMQ保证redis和DB中的数据一致；日常排查线上问题，对系统性能进行优化。 

#### 去O切换工具

​       该系统为业务方提供统一的DAO层切换工具。业务系统只需添加几个bean配置便可以在运行时平滑的从oracle切换到mysql，大大减少业务系统代码开发量，对业务代码的嵌入不多，降低在去O工作上的人力支出。

​       该系统全部有我开发。切换工具的整体思想是让系统中存在3种DAO对象，mysql对应的DAO、oracle对应的DAO和用于切换的DAO，往service层中注入用于切换的DAO，在用于切换的DAO中选择使用mysql对应的DAO还是oracle对应的DAO。其实现是在BeanFactoryPostProcessor中添加用于切换的DAO的beanDefinition信息，在spring的refresh的事件监听中将mysql对应的DAO和oracle对应的DAO当作属性放入用于切换的DAOBean中，事务方面的切换是通过druid的HighAvailableDataSource来切换TransactionManager的datasource属性来实现的。

#### 分布式唯一ID

​        该系统为需要分库分表的业务系统提供唯一ID，也为依赖oracle序列号的系统在做去O改造时的提供统一的替换方案。该系统提供两种实现：

​        一种是依赖数据库，保证一定时间内不重复，此种实现方式全部有我开发。其具体实现是，首先在数据库中存储业务系统需要的序列号的当前值(seqValue)，最小值，最大值，以及每次从数据库中获取序列号的个数(step)，等信息，然后客户端通过dubbo调用访问服务端，服务端从数据库中获取序列号的信息，把序列号的最新值(seqValue+step)更新到数据库中，再把seqValue和seqValue+step返回给客户端，客户端从seqValue开始依次取值作为唯一ID，取到seqValue+step时再开始下一次dubbo调用；当取到序列号的最大值时，会再次重新从最小值开始获取序列号，所以只保证一定时间内不重复。

​        另一种实现是使用snowflake算法，提供19(保证75年内唯一)和16(保证32小时内唯一)两种长度的唯一ID，该系统我主要负责修复时钟回调问题，以及后续维护。其具体实现是使用时间戳+自增序列+机器分配标识+机房分配标示组成64位数字ID。

#### 其他

- 使用阿里开源的datax工具支持数据同步
- 使用ant.design.pro开发了一系列团队内部使用的前端界面
- 维护测试环境的分组功能，开发kafka的分组功能
- 入司第一年获得优秀新人奖，第二年获得责任担当奖
- 获得两份第一作者的专利
- 参与团队各种娱乐活动策划

---



## 技能清单

- 熟悉springramework, mybatis框架
- 熟悉druid,dubbo框架
- 熟悉mysql,redis
- 熟悉svn,git
- 乐于排查各种疑难杂症

---



## 自我评价

态度踏实认真，做事有责任心。

学习能力较强，以不断学习为人生目标。

性格开朗活泼，可以承担团队的气氛组。

