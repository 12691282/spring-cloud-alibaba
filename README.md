原项目地址：https://github.com/spring-cloud-incubator/spring-cloud-alibaba

Spring Cloud Alibaba 致力于提供微服务开发的一站式解决方案。此项目包含开发分布式应用微服务的必需组件，方便开发者通过 Spring Cloud 编程模型轻松使用这些组件来开发分布式应用服务。

依托 Spring Cloud Alibaba，您只需要添加一些注解和少量配置，就可以将 Spring Cloud 应用接入阿里微服务解决方案，通过阿里中间件来迅速搭建分布式应用系统。

参考文档 请查看 WIKI 。

为 Spring Cloud Alibaba 贡献代码请参考 如何贡献 。
主要功能

    服务限流降级：默认支持 WebServlet、WebFlux, OpenFeign、RestTemplate、Spring Cloud Gateway, Zuul, Dubbo 和 RocketMQ 限流降级功能的接入，可以在运行时通过控制台实时修改限流降级规则，还支持查看限流降级 Metrics 监控。
    服务注册与发现：适配 Spring Cloud 服务注册与发现标准，默认集成了 Ribbon 的支持。
    分布式配置管理：支持分布式系统中的外部化配置，配置更改时自动刷新。
    消息驱动能力：基于 Spring Cloud Stream 为微服务应用构建消息驱动能力。
    分布式事务：使用 @GlobalTransactional 注解， 高效并且对业务零侵入地解决分布式事务问题。。
    阿里云对象存储：阿里云提供的海量、安全、低成本、高可靠的云存储服务。支持在任何应用、任何时间、任何地点存储和访问任意类型的数据。
    分布式任务调度：提供秒级、精准、高可靠、高可用的定时（基于 Cron 表达式）任务调度服务。同时提供分布式的任务执行模型，如网格任务。网格任务支持海量子任务均匀分配到所有 Worker（schedulerx-client）上执行。
    阿里云短信服务：覆盖全球的短信服务，友好、高效、智能的互联化通讯能力，帮助企业迅速搭建客户触达通道。

更多功能请参考 Roadmap。
组件

Sentinel：把流量作为切入点，从流量控制、熔断降级、系统负载保护等多个维度保护服务的稳定性。

Nacos：一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。

RocketMQ：一款开源的分布式消息系统，基于高可用分布式集群技术，提供低延时的、高可靠的消息发布与订阅服务。

Dubbo：Apache Dubbo™ 是一款高性能 Java RPC 框架。

Seata：阿里巴巴开源产品，一个易于使用的高性能微服务分布式事务解决方案。

Alibaba Cloud ACM：一款在分布式架构环境中对应用配置进行集中管理和推送的应用配置中心产品。

Alibaba Cloud OSS: 阿里云对象存储服务（Object Storage Service，简称 OSS），是阿里云提供的海量、安全、低成本、高可靠的云存储服务。您可以在任何应用、任何时间、任何地点存储和访问任意类型的数据。

Alibaba Cloud SchedulerX: 阿里中间件团队开发的一款分布式任务调度产品，提供秒级、精准、高可靠、高可用的定时（基于 Cron 表达式）任务调度服务。

Alibaba Cloud SMS: 覆盖全球的短信服务，友好、高效、智能的互联化通讯能力，帮助企业迅速搭建客户触达通道。

更多组件请参考 Roadmap。
如何构建

    master 分支对应的是 Spring Cloud Greenwich，最低支持 JDK 1.8。
    finchley 分支对应的是 Spring Cloud Finchley，最低支持 JDK 1.8。
    1.x 分支对应的是 Spring Cloud Edgware，最低支持 JDK 1.7。

Spring Cloud 使用 Maven 来构建，最快的使用方式是将本项目 clone 到本地，然后执行以下命令：

./mvnw install

执行完毕后，项目将被安装到本地 Maven 仓库。
如何使用
如何引入依赖

如果需要使用已发布的版本，在 dependencyManagement 中添加如下配置。

<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.alibaba.cloud</groupId>
            <artifactId>spring-cloud-alibaba-dependencies</artifactId>
            <version>2.1.0.RELEASE</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>

然后在 dependencies 中添加自己所需使用的依赖即可使用。
演示 Demo

为了演示如何使用，Spring Cloud Alibaba 项目包含了一个子模块spring-cloud-alibaba-examples。此模块中提供了演示用的 example ，您可以阅读对应的 example 工程下的 readme 文档，根据里面的步骤来体验。

Example 列表：

Sentinel Example

Nacos Config Example

Nacos Discovery Example

RocketMQ Example

Seata Example

Alibaba Cloud OSS Example

Alibaba Cloud ANS Example

Alibaba Cloud ACM Example

Alibaba Cloud SchedulerX Example
版本管理规范

项目的版本号格式为 x.x.x 的形式，其中 x 的数值类型为数字，从 0 开始取值，且不限于 0~9 这个范围。项目处于孵化器阶段时，第一位版本号固定使用 0，即版本号为 0.x.x 的格式。

由于 Spring Boot 1 和 Spring Boot 2 在 Actuator 模块的接口和注解有很大的变更，且 spring-cloud-commons 从 1.x.x 版本升级到 2.0.0 版本也有较大的变更，因此我们采取跟 SpringBoot 版本号一致的版本:

    1.5.x 版本适用于 Spring Boot 1.5.x
    2.0.x 版本适用于 Spring Boot 2.0.x
    2.1.x 版本适用于 Spring Boot 2.1.x
