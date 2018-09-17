---
title: 使用托管调试助手诊断错误
ms.date: 08/14/2018
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b745fa6a78ab2a7ab0b3a94c9921883d3c56c1b7
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45750279"
---
# <a name="diagnose-errors-with-managed-debugging-assistants"></a>诊断错误使用托管调试助手

托管调试助手 (MDA) 是调试辅助程序，它与公共语言运行时 (CLR) 一起工作以提供关于运行时状态的信息。 这些助手可生成关于你无法通过其他方式捕获的运行时事件的信息性消息。 可以使用 MDA 隔离在托管代码和非托管代码之间转换时发生的、难以发现的应用程序 Bug。

你可以[启用或禁用](#enable-and-disable-mdas)通过添加到 Windows 注册表项或通过设置环境变量的所有 Mda。 可使用应用程序配置设置来启用特定的 MDA。 可以在应用程序的配置文件中为某些单独的 MDA 设置其他配置设置。 由于将在加载运行时后分析这些配置文件，因此必须在托管应用程序启动之前启用 MDA。 不能为已经启动的应用程序启用 MDA。

下表列出了使用.NET Framework 附带的 Mda:

|||
|-|-|
|[asynchronousThreadAbort](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[bindingFailure](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|
|[callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|
|[dangerousThreadingAPI](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[dateTimeInvalidLocalFormat](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|
|[dirtyCastAndCallOnInterface](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[disconnectedContext](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|
|[dllMainReturnsFalse](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[exceptionSwallowedOnCallFromCom](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|
|[failedQI](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[fatalExecutionEngineError](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|
|[gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|
|[illegalPrepareConstrainedRegion](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|
|[invalidCERCall](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|
|[invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|
|[invalidMemberDeclaration](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|
|[invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[jitCompilationStart](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|
|[loaderLock](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[loadFromContext](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|
|[marshalCleanupError](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|
|[memberInfoCacheCreation](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[moduloObjectHashcode](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|
|[nonComVisibleBaseClass](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[notMarshalable](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|
|[openGenericCERCall](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|
|[pInvokeLog](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|
|[raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[reentrancy](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|
|[releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|
|[streamWriterBufferedDataLost](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[virtualCERCall](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|

默认情况下，.NET Framework 会为所有托管调试器激活 MDA 的子集。 可以查看通过选择 Visual Studio 中设置的默认**Windows** > **异常设置**上**调试**菜单，然后展开**托管调试助手**列表。

![在 Visual Studio 中的异常设置窗口](media/diagnosing-errors-with-managed-debugging-assistants/exception-settings-mdas.png)

## <a name="enable-and-disable-mdas"></a>启用和禁用 Mda

可使用注册表项、环境变量和应用程序配置设置，启用和禁用 MDA。 若要使用应用程序配置设置，必须启用注册表项或环境变量。

> [!TIP]
> 而不是禁用 Mda，可防止 Visual Studio 时收到 MDA 通知时显示 MDA 对话框。 为此，请选择**Windows** > **异常设置**上**调试**菜单中，展开**托管调试助手**列表，然后选择或清除**中断时引发**为单个 MDA 的复选框。

### <a name="registry-key"></a>注册表项

若要启用 Mda，请添加**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\。NETFramework\MDA** Windows 注册表中的子项 （类型为 REG_SZ，值为 1）。 将下面的示例复制到一个名为文本文件*MDAEnable.reg*。打开 Windows 注册表编辑器 (RegEdit.exe)，并从**文件**菜单中，选择**导入**。 选择*MDAEnable.reg*文件以在该计算机上启用 Mda。 将子项设置为字符串值**1** (不是 DWORD 值的**1**) 使读取 MDA 设置从*ApplicationName.suffix*。 文件。 例如，Notepad 的 MDA 配置文件将被命名为 notepad.exe.mda.config。

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]
"MDA"="1"
```

如果计算机在 64 位操作系统上运行 32 位应用程序，应按下方所示设置 MDA 密钥：

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]
"MDA"="1"
```

请参阅[特定于应用程序的配置设置](#application-specific-configuration-settings)有关详细信息。 可以使用 COMPLUS_MDA 环境变量重写注册表设置。 请参阅[环境变量](#environment-variable)有关详细信息。

若要禁用 Mda，请将 MDA 子项设置为**0** （零） 使用 Windows 注册表编辑器。

默认情况下，即使未添加该注册表项，有些 MDA 也会在运行附加到调试器的应用程序时启用。 您可以通过运行禁用这些助手*MDADisable.reg*文件中，如在本部分中前面所述。

### <a name="environment-variable"></a>环境变量

还可以通过环境变量 COMPLUS_MDA 控制 MDA 激活，此变量可重写注册表项。 COMPLUS_MDA 字符串是一个区分大小写、以分号分隔的 MDA 名称列表或其他特殊控制字符串。 在托管或非托管调试器下启动将默认启用一组 MDA。 这是通过在环境变量或注册表项的值前面，隐式附加默认在调试器下启用的、以分号分隔的 MDA 的列表来实现的。 特殊控制字符串如下所示：

- `0` - 停用所有 MDA。

- `1` - 从 ApplicationName.mda.configg 读取 MDA 设置。

- `managedDebugger` - 显式激活在调试器下启动托管可执行文件时隐式激活的所有 MDA。

- `unmanagedDebugger` - 显式激活在调试器下启动非托管可执行文件时隐式激活的所有 MDA。

如果存在冲突的设置，则最新的设置将重写先前的设置：

- `COMPLUS_MDA=0` 禁用所有 MDA，包括那些在调试器下隐式启用的 MDA。

- 除了调试器下隐式启用的所有 MDA，`COMPLUS_MDA=gcUnmanagedToManaged` 还启用 `gcUnmanagedToManaged`。

- `COMPLUS_MDA=0;gcUnmanagedToManaged` 启用 `gcUnmanagedToManaged`，但是禁用将在调试器下隐式启用的 MDA。

### <a name="application-specific-configuration-settings"></a>特定于应用程序的配置设置

可以在应用程序的 MDA 配置文件中单独地启用、禁用和配置某些助手。 若要使用用于配置 MDA 的应用程序配置文件，必须设置 MDA 注册表项或 COMPLUS_MDA 环境变量。 应用程序配置文件通常与应用程序的可执行文件 (.exe) 位于同一目录中。 文件名采用“ApplicationName.mda.config”形式；例如，notepad.exe.mda.config。在应用程序配置文件中启用的助手可能包含专门设计用于控制该助手的行为的特性或元素。

下面的示例演示如何启用和配置[封送处理](../../../docs/framework/debug-trace-profile/marshaling-mda.md):

```xml
<mdaConfig>
  <assistants>
    <marshaling>
      <methodFilter>
        <match name="*"/>
      </methodFilter>
      <fieldFilter>
        <match name="*"/>
      </fieldFilter>
    </marshaling>
  </assistants>
</mdaConfig>
```

对于应用程序中每个托管到非托管的转换，`Marshaling` MDA 会发出有关正封送到非托管类型的托管类型信息。 `Marshaling` MDA 还可以筛选的方法的名称，并按提供的结构字段**methodFilter**并**fieldFilter**子元素分别。

下面的示例演示如何使用其默认设置启用多个 Mda:

```xml
<mdaConfig>
  <assistants>
    <illegalPrepareConstrainedRegion />
    <invalidCERCall />
    <openGenericCERCall />
    <virtualCERCall />
  </assistants>
</mdaConfig>
```

> [!IMPORTANT]
> 若在配置文件中指定了多个助手，则必须按字母顺序列出这些助手。 例如，若要同时启用 `virtualCERCall` 和 `invalidCERCall` MDA，则必须先添加 `<invalidCERCall />` 项，再添加 `<virtualCERCall />` 项。 如果这些项未按字母顺序排列，将显示未处理的无效配置文件异常消息。

## <a name="mda-exceptions"></a>MDA 异常

启用 MDA 后，它处于活动状态甚至当你的代码是不在调试器下执行。 如果在调试器不存在时引发 MDA 事件，尽管这不是未经处理的异常，事件消息也会出现在未经处理的异常对话框中。 若要避免出现该对话框，请在代码未在调试环境中执行时，移除 MDA 启用设置。

当你的代码执行在 Visual Studio 集成的开发环境 (IDE) 中时，可以避免针对特定 MDA 事件出现的异常对话框。 为此，请在**调试**菜单中，选择**Windows** > **异常设置**。 在中**异常设置**窗口中，展开**托管调试助手**列表中，，然后清除**中断时引发**为单个 MDA 的复选框。 此外可以使用此对话框*启用*MDA 异常对话框的显示。

## <a name="mda-output"></a>MDA 输出

MDA 输出结果类似于下面的示例，其中显示了从输出`PInvokeStackImbalance`MDA:

**PInvoke 函数的调用 MDATest ！MDATest.Program::StdCall 具有使堆栈不平衡。这可能是因为托管的 PInvoke 签名与非托管的目标签名不匹配。检查的调用约定和 PInvoke 签名的参数匹配的目标的非托管的签名。**

## <a name="see-also"></a>请参阅

- [调试、跟踪和分析](../../../docs/framework/debug-trace-profile/index.md)
