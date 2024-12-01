# seata-client-re-create-test

- For https://github.com/apache/shardingsphere/issues/29052 and https://github.com/apache/incubator-seata/issues/7039 .

- Verified unit test under Ubuntu 22.04.4 LTS with `SDKMAN!` and `Docker CE`.

```shell
sdk install java 23-open

git clone git@github.com:linghengqian/seata-client-re-create-test.git
cd ./seata-client-re-create-test/
sdk use java 23-open
./mvnw -T 1C clean test
```

- The log is as follows.


```shell
$ ./mvnw -T 1C clean test
[INFO] Scanning for projects...
[INFO] 
[INFO] Using the MultiThreadedBuilder implementation with a thread count of 16
[INFO] 
[INFO] ---------< io.github.linghengqian:seata-client-re-create-test >---------
[INFO] Building seata-client-re-create-test 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ seata-client-re-create-test ---
[INFO] Deleting /home/linghengqian/TwinklingLiftWorks/git/public/seata-client-re-create-test/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ seata-client-re-create-test ---
[INFO] skip non existing resourceDirectory /home/linghengqian/TwinklingLiftWorks/git/public/seata-client-re-create-test/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ seata-client-re-create-test ---
[INFO] No sources to compile
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ seata-client-re-create-test ---
[INFO] Copying 4 resources from src/test/resources to target/test-classes
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ seata-client-re-create-test ---
[INFO] Recompiling the module because of changed source code.
[INFO] Compiling 1 source file with javac [debug target 23] to target/test-classes
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ seata-client-re-create-test ---
[INFO] Using auto detected provider org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running io.github.linghengqian.SimpleTest
[ERROR] 2024-12-01 11:40:24.972 [main] o.a.s.config.ConfigurationFactory - failed to load non-spring configuration :not found service provider for : org.apache.seata.config.ConfigurationProvider
org.apache.seata.common.loader.EnhancedServiceNotFoundException: not found service provider for : org.apache.seata.config.ConfigurationProvider
[ERROR] 2024-12-01 11:40:33.112 [main] o.a.s.c.r.n.NettyClientChannelManager - 0304 register RM failed.
org.apache.seata.common.exception.FrameworkException: can not connect to services-server.
        at org.apache.seata.core.rpc.netty.NettyClientBootstrap.getNewChannel(NettyClientBootstrap.java:181)
        at org.apache.seata.core.rpc.netty.NettyPoolableFactory.makeObject(NettyPoolableFactory.java:58)
        at org.apache.seata.core.rpc.netty.NettyPoolableFactory.makeObject(NettyPoolableFactory.java:34)
        at org.apache.commons.pool.impl.GenericKeyedObjectPool.borrowObject(GenericKeyedObjectPool.java:1220)
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.doConnect(NettyClientChannelManager.java:288)
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.acquireChannel(NettyClientChannelManager.java:110)
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.doReconnect(NettyClientChannelManager.java:233)
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.doReconnect(NettyClientChannelManager.java:212)
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.initReconnect(NettyClientChannelManager.java:176)
        at org.apache.seata.core.rpc.netty.TmNettyRemotingClient.initConnection(TmNettyRemotingClient.java:291)
        at org.apache.seata.core.rpc.netty.TmNettyRemotingClient.init(TmNettyRemotingClient.java:191)
        at org.apache.seata.tm.TMClient.init(TMClient.java:47)
        at org.apache.seata.tm.TMClient.init(TMClient.java:34)
        at io.github.linghengqian.SimpleTest.extracted(SimpleTest.java:39)
        at io.github.linghengqian.SimpleTest.lambda$test$1(SimpleTest.java:29)
        at org.junit.jupiter.api.AssertDoesNotThrow.assertDoesNotThrow(AssertDoesNotThrow.java:49)
        at org.junit.jupiter.api.AssertDoesNotThrow.assertDoesNotThrow(AssertDoesNotThrow.java:36)
        at org.junit.jupiter.api.Assertions.assertDoesNotThrow(Assertions.java:3199)
        at io.github.linghengqian.SimpleTest.test(SimpleTest.java:29)
        at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:103)
        at java.base/java.lang.reflect.Method.invoke(Method.java:580)
        at org.junit.platform.commons.util.ReflectionUtils.invokeMethod(ReflectionUtils.java:766)
        at org.junit.jupiter.engine.execution.MethodInvocation.proceed(MethodInvocation.java:60)
        at org.junit.jupiter.engine.execution.InvocationInterceptorChain$ValidatingInvocation.proceed(InvocationInterceptorChain.java:131)
        at org.junit.jupiter.engine.extension.TimeoutExtension.intercept(TimeoutExtension.java:156)
        at org.junit.jupiter.engine.extension.TimeoutExtension.interceptTestableMethod(TimeoutExtension.java:147)
        at org.junit.jupiter.engine.extension.TimeoutExtension.interceptTestMethod(TimeoutExtension.java:86)
        at org.junit.jupiter.engine.execution.InterceptingExecutableInvoker$ReflectiveInterceptorCall.lambda$ofVoidMethod$0(InterceptingExecutableInvoker.java:103)
        at org.junit.jupiter.engine.execution.InterceptingExecutableInvoker.lambda$invoke$0(InterceptingExecutableInvoker.java:93)
        at org.junit.jupiter.engine.execution.InvocationInterceptorChain$InterceptedInvocation.proceed(InvocationInterceptorChain.java:106)
        at org.junit.jupiter.engine.execution.InvocationInterceptorChain.proceed(InvocationInterceptorChain.java:64)
        at org.junit.jupiter.engine.execution.InvocationInterceptorChain.chainAndInvoke(InvocationInterceptorChain.java:45)
        at org.junit.jupiter.engine.execution.InvocationInterceptorChain.invoke(InvocationInterceptorChain.java:37)
        at org.junit.jupiter.engine.execution.InterceptingExecutableInvoker.invoke(InterceptingExecutableInvoker.java:92)
        at org.junit.jupiter.engine.execution.InterceptingExecutableInvoker.invoke(InterceptingExecutableInvoker.java:86)
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.lambda$invokeTestMethod$8(TestMethodTestDescriptor.java:217)
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.invokeTestMethod(TestMethodTestDescriptor.java:213)
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.execute(TestMethodTestDescriptor.java:138)
        at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.execute(TestMethodTestDescriptor.java:68)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$6(NodeTestTask.java:156)
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:146)
        at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$9(NodeTestTask.java:144)
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:143)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:100)
        at java.base/java.util.ArrayList.forEach(ArrayList.java:1597)
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:41)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$6(NodeTestTask.java:160)
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:146)
        at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$9(NodeTestTask.java:144)
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:143)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:100)
        at java.base/java.util.ArrayList.forEach(ArrayList.java:1597)
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:41)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$6(NodeTestTask.java:160)
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:146)
        at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:137)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$9(NodeTestTask.java:144)
        at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:143)
        at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:100)
        at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.submit(SameThreadHierarchicalTestExecutorService.java:35)
        at org.junit.platform.engine.support.hierarchical.HierarchicalTestExecutor.execute(HierarchicalTestExecutor.java:57)
        at org.junit.platform.engine.support.hierarchical.HierarchicalTestEngine.execute(HierarchicalTestEngine.java:54)
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:198)
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:169)
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:93)
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.lambda$execute$0(EngineExecutionOrchestrator.java:58)
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.withInterceptedStreams(EngineExecutionOrchestrator.java:141)
        at org.junit.platform.launcher.core.EngineExecutionOrchestrator.execute(EngineExecutionOrchestrator.java:57)
        at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:103)
        at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:85)
        at org.junit.platform.launcher.core.DelegatingLauncher.execute(DelegatingLauncher.java:47)
        at org.apache.maven.surefire.junitplatform.LazyLauncher.execute(LazyLauncher.java:56)
        at org.apache.maven.surefire.junitplatform.JUnitPlatformProvider.execute(JUnitPlatformProvider.java:184)
        at org.apache.maven.surefire.junitplatform.JUnitPlatformProvider.invokeAllTests(JUnitPlatformProvider.java:148)
        at org.apache.maven.surefire.junitplatform.JUnitPlatformProvider.invoke(JUnitPlatformProvider.java:122)
        at org.apache.maven.surefire.booter.ForkedBooter.runSuitesInProcess(ForkedBooter.java:385)
        at org.apache.maven.surefire.booter.ForkedBooter.execute(ForkedBooter.java:162)
        at org.apache.maven.surefire.booter.ForkedBooter.run(ForkedBooter.java:507)
        at org.apache.maven.surefire.booter.ForkedBooter.main(ForkedBooter.java:495)
Caused by: org.apache.seata.common.exception.FrameworkException: connect failed, can not connect to services-server.
        at org.apache.seata.core.rpc.netty.NettyClientBootstrap.getNewChannel(NettyClientBootstrap.java:176)
        ... 87 common frames omitted
Caused by: io.netty.channel.AbstractChannel$AnnotatedConnectException: 连接被拒绝: /127.0.0.1:32836
Caused by: java.net.ConnectException: 连接被拒绝
        at java.base/sun.nio.ch.Net.pollConnect(Native Method)
        at java.base/sun.nio.ch.Net.pollConnectNow(Net.java:682)
        at java.base/sun.nio.ch.SocketChannelImpl.finishConnect(SocketChannelImpl.java:1062)
        at io.netty.channel.socket.nio.NioSocketChannel.doFinishConnect(NioSocketChannel.java:337)
        at io.netty.channel.nio.AbstractNioChannel$AbstractNioUnsafe.finishConnect(AbstractNioChannel.java:334)
        at io.netty.channel.nio.NioEventLoop.processSelectedKey(NioEventLoop.java:776)
        at io.netty.channel.nio.NioEventLoop.processSelectedKeysOptimized(NioEventLoop.java:724)
        at io.netty.channel.nio.NioEventLoop.processSelectedKeys(NioEventLoop.java:650)
        at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:562)
        at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:997)
        at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
        at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
        at java.base/java.lang.Thread.run(Thread.java:1575)
[ERROR] Tests run: 1, Failures: 1, Errors: 0, Skipped: 0, Time elapsed: 14.57 s <<< FAILURE! -- in io.github.linghengqian.SimpleTest
[ERROR] io.github.linghengqian.SimpleTest.test -- Time elapsed: 14.54 s <<< FAILURE!
org.opentest4j.AssertionFailedError: Unexpected exception thrown: org.apache.seata.common.exception.FrameworkException: can not connect to [127.0.0.1:32836]
        at org.junit.jupiter.api.AssertionFailureBuilder.build(AssertionFailureBuilder.java:152)
        at org.junit.jupiter.api.AssertDoesNotThrow.createAssertionFailedError(AssertDoesNotThrow.java:84)
        at org.junit.jupiter.api.AssertDoesNotThrow.assertDoesNotThrow(AssertDoesNotThrow.java:53)
        at org.junit.jupiter.api.AssertDoesNotThrow.assertDoesNotThrow(AssertDoesNotThrow.java:36)
        at org.junit.jupiter.api.Assertions.assertDoesNotThrow(Assertions.java:3199)
        at io.github.linghengqian.SimpleTest.test(SimpleTest.java:29)
        at java.base/java.lang.reflect.Method.invoke(Method.java:580)
        at java.base/java.util.ArrayList.forEach(ArrayList.java:1597)
        at java.base/java.util.ArrayList.forEach(ArrayList.java:1597)
Caused by: org.apache.seata.common.exception.FrameworkException: can not connect to [127.0.0.1:32836]
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.doReconnect(NettyClientChannelManager.java:251)
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.doReconnect(NettyClientChannelManager.java:212)
        at org.apache.seata.core.rpc.netty.NettyClientChannelManager.initReconnect(NettyClientChannelManager.java:176)
        at org.apache.seata.core.rpc.netty.TmNettyRemotingClient.initConnection(TmNettyRemotingClient.java:291)
        at org.apache.seata.core.rpc.netty.TmNettyRemotingClient.init(TmNettyRemotingClient.java:191)
        at org.apache.seata.tm.TMClient.init(TMClient.java:47)
        at org.apache.seata.tm.TMClient.init(TMClient.java:34)
        at io.github.linghengqian.SimpleTest.extracted(SimpleTest.java:39)
        at io.github.linghengqian.SimpleTest.lambda$test$1(SimpleTest.java:29)
        at org.junit.jupiter.api.AssertDoesNotThrow.assertDoesNotThrow(AssertDoesNotThrow.java:49)
        ... 6 more

[INFO] 
[INFO] Results:
[INFO] 
[ERROR] Failures: 
[ERROR]   SimpleTest.test:29 Unexpected exception thrown: org.apache.seata.common.exception.FrameworkException: can not connect to [127.0.0.1:32836]
[INFO] 
[ERROR] Tests run: 1, Failures: 1, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  17.355 s (Wall Clock)
[INFO] Finished at: 2024-12-01T11:40:34+08:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:3.2.5:test (default-test) on project seata-client-re-create-test: There are test failures.
[ERROR] 
[ERROR] Please refer to /home/linghengqian/TwinklingLiftWorks/git/public/seata-client-re-create-test/target/surefire-reports for the individual test results.
[ERROR] Please refer to dump files (if any exist) [date].dump, [date]-jvmRun[N].dump and [date].dumpstream.
[ERROR] -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException
```
