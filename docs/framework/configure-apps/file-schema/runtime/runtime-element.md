---
title: <runtime> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#runtime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime
helpviewer_keywords:
- <runtime> element
- runtime element
- container tags, <runtime> element
ms.assetid: 1eb2fae3-de4b-45b6-852f-517c39b751bd
ms.openlocfilehash: 3825ae7c3e35193cb835981600fe1ef83097cd2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430455"
---
# <a name="runtime-element"></a>\<runtime> Element

Provides information used by the common language runtime to configure applications.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;\<runtime>

## <a name="syntax"></a>语法

```xml
<runtime>
</runtime>
```

## <a name="attributes-and-elements"></a>特性和元素

The following sections describe child elements and parent elements.

### <a name="attributes"></a>特性

无。

### <a name="child-elements"></a>子元素

|元素|描述|
|-------------|-----------------|
|[\<alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md)|指定 Windows 标识始终流经异步点，而不考虑执行模拟的方式。|
|[\<AppContextSwitchOverrides>](appcontextswitchoverrides-element.md)|定义 <xref:System.AppContext> 类使用的一个或多个开关，用于提供新功能的选择退出机制。|
|[\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)|指定为过程中的默认应用程序域提供应用程序域管理器的程序集。|
|[\<appDomainManagerType>](appdomainmanagertype-element.md)|指定用作默认应用程序域的应用程序域管理器的类型。|
|[\<appDomainResourceMonitoring>](appdomainresourcemonitoring-element.md)|指示运行时在过程的生命周期过程中收集所有应用程序域的统计数据。|
|[\<assemblyBinding>](assemblybinding-element-for-runtime.md)|包含有关程序集版本重定向和程序集位置的信息。|
|[\<bypassTrustedAppStrongNames>](bypasstrustedappstrongnames-element.md)|指定是否应绕过对受信任的程序集进行强名称验证。|
|[\<CompatSortNLSVersion>](compatsortnlsversion-element.md)|Specifies that the runtime should use legacy sorting behavior when performing string comparisons.|
|[\<developmentMode>](developmentmode-element.md)|指定运行时是否搜索由 DEVPATH 环境变量指定的目录中的程序集。|
|[\<disableCachingBindingFailures>](disablecachingbindingfailures-element.md)|Specifies whether the caching of binding failures, which is the default behavior in the .NET Framework version 2.0, is disabled.|
|[\<disableCommitThreadStack>](disablecommitthreadstack-element.md)|指定在线程启动时是否提交完整线程堆栈。|
|[\<disableFusionUpdatesFromADManager>](disablefusionupdatesfromadmanager-element.md)|指定是否禁用允许运行时主机为应用程序域重写配置设置的默认行为。|
|[\<EnableAmPmParseAdjustment>](enableampmparseadjustment-element.md)|确定日期和时间分析方法是否使用调整后的一组规则来分析仅包含天、月、小时和 AM/PM 指示符的日期字符串。|
|[\<enforceFIPSPolicy>](enforcefipspolicy-element.md)|指定是否强制执行以下计算机配置要求：加密算法必须符合美国联邦信息处理标准 (FIPS)。|
|[\<etwEnable>](etwenable-element.md)|指定是否为公共语言运行时事件启用 Windows 事件跟踪 (ETW)。|
|[\<forcePerformanceCounterUniqueSharedMemoryReads>](forceperformancecounteruniquesharedmemoryreads-element.md)|指定 PerfCounter.dll 是否使用 .NET Framework 版本 1.1 应用程序中的 CategoryOptions 注册表设置，以确定是否加载来自特定于类别的共享内存或全局内存的性能计数器数据。|
|[\<gcAllowVeryLargeObjects>](gcallowverylargeobjects-element.md)|在 64 位平台上，启用总大小大于 2 千兆字节 (GB) 的数组。|
|[\<gcConcurrent>](gcconcurrent-element.md)|Specifies whether the common language runtime runs garbage collection concurrently.|
|[\<GCCpuGroup>](gccpugroup-element.md)|指定垃圾回收是否支持多个 CPU 组。|
|[\<GCHeapAffinitizeMask>](gcheapaffinitizemask-element.md)|Defines the affinity between garbage collection heaps and individual processors.|
|[\<GCHeapCount>](gcheapcount-element.md)|Specifies the number of heaps/threads to use for server garbage collection.|
|[\<GCLOHThreshold>](gclohthreshold-element.md)|Specifies the threshold size that causes the garbage collector to put objects on the large object heap.|
|[\<GCNoAffinitize>](gcnoaffinitize-element.md)|Specifies whether or not to affinitize server garbage collection threads with CPUs.|
|[\<gcServer>](gcserver-element.md)|指定公共语言运行时是否运行服务器垃圾回收。|
|[\<generatePublisherEvidence>](generatepublisherevidence-element.md)|指定运行时是否使用代码访问安全性 (CAS) 发布服务器策略。|
|[\<legacyCorruptedStateExceptionsPolicy>](legacycorruptedstateexceptionspolicy-element.md)|指定运行时是否允许托管的代码捕获访问冲突和其他损坏状态异常。|
|[\<legacyImpersonationPolicy>](legacyimpersonationpolicy-element.md)|指定 Windows 标识不流经异步点，而不考虑当前线程上执行上下文的流设置。|
|[\<loadfromRemoteSources>](loadfromremotesources-element.md)|指定是否将来自远程源的程序集加载为完全信任。|
|[\<NetFx40_LegacySecurityPolicy>](netfx40-legacysecuritypolicy-element.md)|指定运行时是否使用旧版代码访问安全性 (CAS) 策略。|
|[\<NetFx40_PInvokeStackResilience>](netfx40-pinvokestackresilience-element.md)|指定运行时是否以减慢托管和非托管代码之间的转换速度为代价，在运行时自动修复不正确的平台调用声明。|
|[\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>](netfx45-cultureawarecomparergethashcode-longstrings-element.md)|指定运行时是否使用固定的内存量来计算 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 方法的哈希代码。|
|[\<PreferComInsteadOfRemoting>](prefercominsteadofmanagedremoting-element.md)|指定运行时将使用 COM 互操作来代替跨应用程序域边界的远程。|
|[\<relativeBindForResources>](relativebindforresources-element.md)|优化附属程序集的探测。|
|[\<shadowCopyVerifyByTimeStamp>](shadowcopyverifybytimestamp-element.md)|Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.|
|[\<supportPortability>](supportportability-element.md)|通过禁用将程序集视为等效于应用程序可移植性用途的默认行为来指定应用程序可以在两种不同的 .NET Framework 实现中引用同一程序集。|
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|提供默认内存中对象缓存的配置信息。|
|[\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md)|指定运行时是否跨所有 CPU 组分发托管的线程。|
|[\<ThrowUnobservedTaskExceptions>](throwunobservedtaskexceptions-element.md)|指定未经处理的任务异常是否应终止正在运行的进程。|
|[\<TimeSpan_LegacyFormatMode>](timespan-legacyformatmode-element.md)|指定运行时是否使用 <xref:System.TimeSpan> 值的旧格式。|
|[\<useLegacyJit>](uselegacyjit-element.md)|确定公共语言运行时是否使用实时编译的旧版 64 位 JIT 编译器。|
|[\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md)|指定运行时是否按应用程序域计算字符串的哈希代码。|
|[\<UseSmallInternalThreadStacks>](usesmallinternalthreadstacks-element.md)|请求运行时在创建内部使用的某些线程时使用显式堆栈大小，而不是默认堆栈大小。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|

## <a name="remarks"></a>备注

The child elements in the [\<runtime>](runtime-element.md) section of a configuration file are used by the common language runtime to configure how an application executes. For example, the [\<gcServer>](gcserver-element.md) element determines whether the garbage collector uses workstation garbage collection or server garbage collection, the [\<UseRandomizedStringHashAlgorithm>](userandomizedstringhashalgorithm-element.md) element determines whether the common language runtime calculates hash codes for string on a per-application or a per-application domain basis, and the `AppContextSwitchOverrides` element allows library users to opt in or opt out of changed  functionality provided by a library.

The elements in the [\<runtime>](runtime-element.md) section are read automatically by the common language runtime at application startup. You can also define the configuration file for a non-default application domain by supplying its name to the <xref:System.AppDomainSetup.ConfigurationFile%2A?displayProperty=nameWithType> property; its settings are read automatically when the application domain is loaded. You should rarely, if ever, have a need to directly read the settings in the [\<runtime>](runtime-element.md) section in your application's configuration file.

## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
