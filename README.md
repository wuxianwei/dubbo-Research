# 源码解析

* https://github.com/daniellitoc/dubbo-Research/tree/readme/dubbo-config/dubbo-config-spring
* https://github.com/daniellitoc/dubbo-Research/tree/readme/dubbo-config/dubbo-config-api
* https://github.com/daniellitoc/dubbo-Research/tree/readme/dubbo-common
* https://github.com/daniellitoc/dubbo-Research/tree/readme/dubbo-rpc/dubbo-rpc-api

## dubbo-config-spring

* Spring解析配置源码分析

    * dubbo:application
    * dubbo:module
    * dubbo:registry
    * dubbo:monitor
    * dubbo:provider
    * dubbo:consumer
    * dubbo:protocol
    * dubbo:service
    * dubbo:method
    * dubbo:argument
    * dubbo:reference
    * dubbo:annotation

* Spring Bean源码分析

    * ServiceBean
    * ReferenceBean
    * AnnotationBean

## dubbo-config-api

* Dubbo Config相关类setter/getter源码分析

    * ApplicationConfig
    * ModuleConfig
    * RegistryConfig
    * MonitorConfig
    * ProviderConfig
    * ConsumerConfig
    * ProtocolConfig
    * MethodConfig
    * ArgumentConfig
    * AnnotationBean
    * ServiceConfig
    * ReferenceConfig

* ServiceConfig源码分析

    * public synchronized void export()
    * public synchronized void unexport()

* ReferenceConfig源码分析

    * public synchronized T get()
    * public synchronized void destroy()

## dubbo-common

* ExtensionLoader源码分析

    * ExtensionLoader（ExtensionFactory）
    * ExtensionLoader（非ExtensionFactory）

* Wrapper源码分析

## dubbo-rpc-api

### Dubbo SPI和对应的实现分析（provider/consumer启动、调用）

* com.alibaba.dubbo.common.compiler.Compiler

    * com.alibaba.dubbo.common.compiler.support.AdaptiveCompiler
    * com.alibaba.dubbo.common.compiler.support.JavassistCompiler（未）
    * com.alibaba.dubbo.common.compiler.support.JdkCompiler（未）

* com.alibaba.dubbo.rpc.ProxyFactory

    * com.alibaba.dubbo.rpc.proxy.javassist.JavassistProxyFactory
    * com.alibaba.dubbo.rpc.proxy.AbstractProxyInvoker
    * com.alibaba.dubbo.rpc.proxy.InvokerInvocationHandler
    * com.alibaba.dubbo.rpc.proxy.wrapper.StubProxyFactoryWrapper

* com.alibaba.dubbo.common.threadpool.ThreadPool

    * com.alibaba.dubbo.common.threadpool.support.limited.LimitedThreadPool

* com.alibaba.dubbo.common.serialize.Serialization

    * com.alibaba.dubbo.common.serialize.support.hessian.Hessian2Serialization

* com.alibaba.dubbo.rpc.cluster.ConfiguratorFactory

    * com.alibaba.dubbo.rpc.cluster.configurator.override.OverrideConfiguratorFactory
    * com.alibaba.dubbo.rpc.cluster.configurator.override.OverrideConfigurator
    * com.alibaba.dubbo.rpc.cluster.configurator.absent.AbsentConfiguratorFactory
    * com.alibaba.dubbo.rpc.cluster.configurator.absent.AbsentConfigurator

* com.alibaba.dubbo.rpc.Protocol

* com.alibaba.dubbo.rpc.protocol.ProtocolFilterWrapper

    * com.alibaba.dubbo.rpc.Filter
    * com.alibaba.dubbo.rpc.filter.ActiveLimitFilter（未）
    * com.alibaba.dubbo.rpc.filter.ExecuteLimitFilter（未）
    * com.alibaba.dubbo.rpc.filter.TokenFilter（未）
    * com.alibaba.dubbo.rpc.filter.GenericFilter（未）
    * com.alibaba.dubbo.rpc.filter.GenericImplFilter（未）

* com.alibaba.dubbo.rpc.protocol.ProtocolListenerWrapper

    * com.alibaba.dubbo.rpc.ExporterListener
    * com.alibaba.dubbo.rpc.InvokerListener
    * com.alibaba.dubbo.rpc.listener.ListenerExporterWrapper
    * com.alibaba.dubbo.rpc.listener.ListenerInvokerWrapper

* com.alibaba.dubbo.rpc.support.MockProtocol

    * com.alibaba.dubbo.rpc.support.MockInvoker

* com.alibaba.dubbo.rpc.protocol.injvm.InjvmProtocol

    * com.alibaba.dubbo.rpc.protocol.AbstractExporter
    * com.alibaba.dubbo.rpc.protocol.injvm.InjvmExporter
    * com.alibaba.dubbo.rpc.protocol.AbstractInvoker
    * com.alibaba.dubbo.rpc.protocol.injvm.InjvmInvoker

* com.alibaba.dubbo.rpc.protocol.http.HttpProtocol

    * com.alibaba.dubbo.rpc.protocol.http.HttpProtocol.InternalHandler

* com.alibaba.dubbo.rpc.protocol.dubbo.DubboProtocol

    * com.alibaba.dubbo.rpc.protocol.dubbo.DubboProtocol.ExchangeHandler
    * com.alibaba.dubbo.rpc.protocol.dubbo.DubboExporter
    * com.alibaba.dubbo.remoting.exchange.Exchangers
    * com.alibaba.dubbo.rpc.protocol.dubbo.DubboInvoker
    * com.alibaba.dubbo.rpc.protocol.dubbo.ReferenceCountExchangeClient
    * com.alibaba.dubbo.rpc.protocol.dubbo.LazyConnectExchangeClient

* com.alibaba.dubbo.remoting.exchange.Exchanger

    * com.alibaba.dubbo.remoting.exchange.support.header.HeaderExchanger
    * com.alibaba.dubbo.remoting.exchange.support.header.HeaderExchangeServer
    * com.alibaba.dubbo.remoting.exchange.support.header.HeaderExchangeClient
    * com.alibaba.dubbo.remoting.exchange.support.header.HeaderExchangeHandler
    * com.alibaba.dubbo.remoting.exchange.support.header.HeaderExchangeChannel
    * com.alibaba.dubbo.remoting.Transporters

* com.alibaba.dubbo.remoting.Transporter

    * com.alibaba.dubbo.remoting.transport.netty.NettyTransporter
    * com.alibaba.dubbo.remoting.transport.netty.NettyServer
    * com.alibaba.dubbo.remoting.transport.netty.NettyClient
    * com.alibaba.dubbo.remoting.exchange.support.header.HeartbeatHandler

* com.alibaba.dubbo.remoting.Dispatcher

    * com.alibaba.dubbo.remoting.transport.dispatcher.all.AllDispatcher

* com.alibaba.dubbo.remoting.Codec2

    * com.alibaba.dubbo.rpc.protocol.dubbo.DubboCountCodec（未）
    * com.alibaba.dubbo.rpc.protocol.dubbo.DubboCodec（未）

* com.alibaba.dubbo.rpc.cluster.Cluster

    * com.alibaba.dubbo.rpc.cluster.support.wrapper.MockClusterWrapper
    * com.alibaba.dubbo.rpc.cluster.support.FailoverCluster
    * com.alibaba.dubbo.rpc.cluster.support.FailfastCluster
    * com.alibaba.dubbo.rpc.cluster.support.AvailableCluster
    * com.alibaba.dubbo.rpc.cluster.support.MergeableCluster
    * com.alibaba.dubbo.rpc.cluster.directory.AbstractDirectory
    * com.alibaba.dubbo.rpc.cluster.directory.StaticDirectory
    * com.alibaba.dubbo.registry.integration.RegistryDirectory
    * com.alibaba.dubbo.rpc.cluster.support.wrapper.MockClusterInvoker
    * com.alibaba.dubbo.rpc.cluster.support.AbstractClusterInvoker
    * com.alibaba.dubbo.rpc.cluster.support.FailoverClusterInvoker
    * com.alibaba.dubbo.rpc.cluster.support.FailfastClusterInvoker
    * com.alibaba.dubbo.rpc.cluster.support.MergeableClusterInvoker（未）

* com.alibaba.dubbo.rpc.cluster.Router

* com.alibaba.dubbo.rpc.cluster.LoadBalance

    * com.alibaba.dubbo.rpc.cluster.loadbalance.LeastActiveLoadBalance（未）
    * com.alibaba.dubbo.rpc.cluster.loadbalance.RoundRobinLoadBalance（未）

* com.alibaba.dubbo.registry.integration.RegistryProtocol
* com.alibaba.dubbo.registry.RegistryFactory

    * com.alibaba.dubbo.registry.zookeeper.ZookeeperRegistryFactory
    * com.alibaba.dubbo.registry.zookeeper.ZookeeperRegistry

* com.alibaba.dubbo.remoting.zookeeper.ZookeeperTransporter

    * com.alibaba.dubbo.remoting.zookeeper.curator.CuratorZookeeperTransporter（未）

* com.alibaba.dubbo.remoting.telnet.TelnetHandler（未）
* com.alibaba.dubbo.common.status.StatusChecker（未）