
## 各版本主要功能
    spring 2.5  2007发布  支持注解
    spring 3.0  2009发布  完全利用了Java5的改进，为JEE6提供了支持
    spring 4.0  2013发布  支持Java8
    spring 5.0  2017发布  基于JDK8开发，Reactive响应式编程模型，webflux模块

## 核心四包
    core、beans、context、expression（aop）
    
## beans
    Bean的定义、Bean的解析、Bean的创建

## IOC
    把对象之间的依赖关系用配置文件来管理


### Spring中最核心的两个类
    DefaultListableBeanFactory (XmlBeanFactory)
    
    XmlBeanDefinitionReader里主要方法：doLoadBeanDefinitions
    // 1、根据xml的inputSource加载为Document对象：用到DefaultDocumentLoader，ResourceEntityResolver(DelegatingEntityResolver)
    // 2、根据Document对象注册为BeanDefinitions：用到DefaultBeanDefinitionDocumentReader
    

    几大BeanDefinitionReader：
    
    XmlBeanDefinitionReader
    AnnotationBeanDefinitionReader
    ConfigurationClassBeanDefinitionReader
    PropertiesBeanDefinitionReader





为了区分在 Spring 内部对象的传递和转化过程中，对对象的数据访问所做的限制。
例如 ListableBeanFactory 接口表示这些 Bean 是可列表的，而 HierarchicalBeanFactory 表示的这些 Bean 是有继承关系的，
也就是每个 Bean 有可能有父 Bean。AutowireCapableBeanFactory 接口定义 Bean 的自动装配规则。
这四个接口共同定义了 Bean 的集合、Bean 之间的关系、以及 Bean 行为。


ConfigurableApplicationContext 表示该 Context 是可修改的，也就是在构建 Context 中用户可以动态添加或修改已有的配置信息，
它下面又有多个子类，其中最经常使用的是可更新的 Context，即 AbstractRefreshableApplicationContext 类。


Context 是把资源的加载、解析和描述工作委托给了 ResourcePatternResolver 类



## Spring主要扩展点
    BeanFactoryPostProcessor
    BeanPostProcessor

他们分别是在构建 BeanFactory 和构建 Bean 对象时调用。还有就是 InitializingBean 和 DisposableBean， 
他们分别是在 Bean 实例创建和销毁时被调用。用户可以实现这些接口中定义的方法，Spring 就会在适当的时候调用他们。
还有一个是 FactoryBean 他是个特殊的 Bean，这个 Bean 可以被用户更多的控制




### Maven怎么引入Spring??
在普通java工程使用spring框架，只需如下一个dependency即可
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-context</artifactId>
        <version>4.3.29.RELEASE</version>
    </dependency>
在web工程中引入Spring MVC，只需如下一个dependency即可
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-webmvc</artifactId>
        <version>4.3.29.RELEASE</version>
    </dependency>
在spring boot中



    
## Spring源码常用单词
Delegate	委派
Candidate	候选者
Pluggable	可插拔式
Extractor	抽出器，提取器

decorate	装饰
canonical	最简洁的