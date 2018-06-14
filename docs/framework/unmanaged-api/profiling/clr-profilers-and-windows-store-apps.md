---
title: CLR 探查器和 Windows 应用商店应用
ms.date: 03/30/2017
dev_langs:
- csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a1ed9b6b613b1e4d3e5363ab9995cc81295091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462281"
---
# <a name="clr-profilers-and-windows-store-apps"></a>CLR 探查器和 Windows 应用商店应用
本主题讨论你需要考虑时写入诊断工具来分析托管代码中的 Windows 应用商店应用运行。  它还提供了一些指南，可以修改现有的开发工具，以使它们继续正常工作时针对 Windows 应用商店应用运行时。  若要了解此信息，最好是如果你熟悉公共语言运行时分析 API，已在运行 Windows 桌面应用程序，并且你针对正确现在感兴趣修改该工具的诊断工具中使用此 API若要针对 Windows 应用商店应用程序正确运行。  
  
 本主题包括以下各节：  
  
 [介绍](#Intro)  
 [体系结构和术语](#Arch)  
 [Windows RT 设备](#RT)  
[使用 Windows 运行时 Api](#Consuming)  
[加载探查器 DLL](#Loading)  
 [常见的注意事项，为启动和附加加载](#Common)  
 [启动负载](#Startup)  
 [附加负载](#Attach)  
[在 Windows 应用商店应用程序内部运行](#Running)  
 [停在 Windows 应用商店应用程序 Api](#APIs)  
 [降低的权限](#Permissions)  
 [进程间通信](#Interprocess)  
 [没有关闭通知](#Shutdown)  
[Windows 运行时元数据文件](#Metadata)  
 [托管和非托管 Winmd](#WMDs)  
 [WinMD 文件如下所示的 CLR 模块](#CLRModules)  
 [从 Winmd 读取元数据](#Reading)  
 [修改从 Winmd 元数据](#Modifying)  
 [解决与 Winmd 的程序集引用](#Resolving)  
[内存探查器](#Profilers)  
 [ForceGC 创建一个托管的线程](#ForceGC)  
 [ConditionalWeakTableReferences](#WeakTable)  
[结束语](#Conclusion)  
[资源](#Resources)  
  
<a name="Intro"></a>   
## <a name="introduction"></a>介绍  
 如果你进行了它过去的介绍性段落，然后你熟悉 CLR 分析 API。  您已经编写了一个诊断工具，也对托管的桌面应用程序有效。  现在你想要执行的操作，以便你工具与托管的 Windows 应用商店应用结合使用。  可能是你已尝试进行此项工作，并已发现它不是简单的任务。  事实上，有大量的可能不太明显到所有的工具开发人员的注意事项。  例如：  
  
-   具有严重降低的权限的上下文中运行 Windows 应用商店应用。  
  
-   Windows 元数据文件具有独特特征相比传统的托管模块时。  
  
-   Windows 应用商店应用具有交互性出现故障时挂起自身的一个习惯。  
  
-   由于各种原因，你的进程间通信机制可能不再起作用。  
  
 本主题列出了需要注意的操作以及如何正确处理它们。  
  
 如果你不熟悉 CLR 分析 API，则跳到本主题末尾的资源，若要查找更好地介绍性信息。  
  
 提供有关特定的 Windows Api 和它们的使用方式的详细信息也是本主题的范围之外。  请考虑本主题的起点，并参考 MSDN 若要了解有关此处引用任何 Windows Api 的详细信息。  
  
<a name="Arch"></a>   
## <a name="architecture-and-terminology"></a>体系结构和术语  
 通常，一个诊断工具具有类似下图中所示的体系结构。 它使用术语"探查器，"但许多此类工具转远远超过典型性能或内存分析为领域，如代码覆盖率，模拟对象框架，时程调试，应用程序监视，依次类推。  为简单起见，本主题将继续引用作为探查器的所有这些工具。  
  
 在本主题中使用下列术语：  
  
 应用程序  
 这是应用程序分析探查器。  通常情况下，此应用程序的开发人员现在使用探查器以帮助诊断问题与应用程序。  传统上，此应用程序将 Windows 桌面应用程序，但在本主题中，我们要查找 Windows 应用商店应用。  
  
 探查器 DLL  
 这是将加载到应用程序所分析的进程空间的组件。  此组件，也称为探查器"代理，"将实现[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2，3，等) 接口，并使用[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2，3，等) 接口，以便收集有关分析应用程序和可能的数据修改的应用程序的行为方面。  
  
 探查器用户界面  
 这是一个桌面应用程序与探查器用户交互。  它负责向用户显示应用程序状态并向用户提供了一种来控制经过分析的应用程序的行为。  此组件始终在其自身进程空间，独立于正在分析的应用程序的进程空间中运行。  探查器 UI 还可以充当"附加触发器，"指调用的过程[iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法，使经过分析的应用程序加载在这些情况下，探查器 DLL 没有探查器 DLL在启动时加载。  
  
> [!IMPORTANT]
>  探查器 UI 应保留 Windows 桌面应用程序，即使它用于将控件和在 Windows 应用商店应用上的报表。  不希望能够进行打包和传送你在 Windows 应用商店中的诊断工具。  您的工具需要执行操作，无法执行 Windows 应用商店应用，并提供其中的许多驻留在探查器用户界面。  
  
 在本文档的代码示例假定：  
  
-   探查器 DLL 是编写 c + + 中，因为它必须是本机 DLL，根据 CLR 分析 API 要求。  
  
-   探查器用户界面是用 C# 编写的。  这不是必需的但因为没有在探查器用户界面的进程的语言要求，为什么不选取简洁明了的语言？  
  
<a name="RT"></a>   
### <a name="windows-rt-devices"></a>Windows RT 设备  
 Windows RT 设备非常锁定。  只需第三方探查器无法加载此类设备上。  本文档侧重介绍在 Windows 8 Pc 上。  
  
<a name="Consuming"></a>   
## <a name="consuming-windows-runtime-apis"></a>使用 Windows 运行时 Api  
 在大量的以下各节所述的方案，您探查器用户界面的桌面应用程序需要使用一些新的 Windows 运行时 Api。  你将需要查阅文档以了解可以从桌面应用程序使用的 Windows 运行时 Api，它们的行为不同时是否从调用桌面应用程序和 Windows 应用商店应用。  
  
 如果探查器用户界面在托管代码中编写的将有几个步骤，你将需要执行的操作以使用这些简单的 Windows 运行时 Api。  请参阅[托管桌面应用和 Windows 运行时](http://go.microsoft.com/fwlink/?LinkID=271858)文章了解详细信息。  
  
<a name="Loading"></a>   
## <a name="loading-the-profiler-dll"></a>加载探查器 DLL  
 本部分介绍如何将探查器 UI 导致 Windows 应用商店应用程序加载探查器 DLL。  此部分中讨论的代码位于探查器 UI 桌面应用程序，并且因此涉及在使用安全的桌面应用，但不一定是安全的 Windows 应用商店应用的 Windows Api。  
  
 探查器用户界面可能会导致探查器 DLL 加载到应用程序的进程空间两种方式：  
  
-   在应用程序启动时，由环境变量控制。  
  
-   通过将附加到应用程序启动完成后通过调用[iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)方法。  
  
 第一个障碍之一将获取启动负载测试和附加加载的探查器 DLL 地与 Windows 应用商店应用程序一起正常工作。  加载这两种形式具有共同点注意一些特殊事项，因此让我们开始使用它们。  
  
<a name="Common"></a>   
### <a name="common-considerations-for-startup-and-attach-loads"></a>常见的注意事项，为启动和附加加载  
 **签名探查器 DLL**  
 当 Windows 会尝试加载探查器 DLL 时，它验证探查器 DLL 进行了正确的签名。  否则，默认情况下则加载会失败。 有两种方法可以实现此目的：  
  
-   确保你的探查器 DLL 进行签名。  
  
-   告诉你的用户，他们必须安装开发人员许可证在其 Windows 8 计算机上使用你的工具之前。  这可以从 Visual Studio 或手动从命令提示符处自动完成。  有关详细信息，请参阅[获取开发人员许可证](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)。  
  
 **文件系统权限**  
 Windows 应用商店应用必须有权加载并从它所在的文件系统上的位置执行事件探查器 DLL。  默认情况下，Windows 应用商店应用程序没有此类权限大多数目录，并将任何失败的尝试加载探查器 DLL 将产生如下所示的 Windows 应用程序事件日志中的条目：  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 通常情况下，Windows 应用商店应用仅允许访问一组有限的磁盘上的位置。  每个 Windows 应用商店应用可以访问自己应用程序数据文件夹，以及少量其他区域，在文件系统中为其所有的 Windows 应用商店应用程序被授予访问权限。  最好安装探查器 DLL 某个位置下的 Program Files 或 Program Files (x86)，及其依赖项，因为所有的 Windows 应用商店应用具有读取和默认情况下执行有权限。  
  
<a name="Startup"></a>   
### <a name="startup-load"></a>启动负载  
 通常情况下，在桌面应用中，探查器用户界面提示探查器 DLL 启动负载初始化包含所需的 CLR 分析 API 环境变量的环境块 (即， `COR_PROFILER`， `COR_ENABLE_PROFILING`，和`COR_PROFILER_PATH`)，和然后使用该环境块创建一个新进程。  同样适用于 Windows 应用商店应用，但不同的机制。  
  
 **不运行提升**  
 如果进程尝试生成 Windows 应用商店应用程序进程 B 进程 A 应在运行中等规模的完整性级别时，不能在高完整性级别 （即，不提升的权限）。  这意味着你探查器的 UI 应在中等规模的完整性级别运行，或它必须生成中等规模的完整性级别负责启动 Windows 应用商店应用上的另一个桌面进程。  
  
 **选择 Windows 应用商店应用迁移到配置文件**  
 首先，你将想要要求你探查器用户启动的 Windows 应用商店应用程序。  对于桌面应用，可能会显示文件浏览对话框，然后用户将查找并选择的.exe 文件。  但 Windows 应用商店应用是不同的并使用一个浏览对话框没有任何意义。  相反，它是更好的做法显示用户已安装了该用户就可以从选择的 Windows 应用商店应用的列表。  
  
 你可以使用[PackageManager 类](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx)生成此列表。  `PackageManager` 是可用于桌面应用的 Windows 运行时类和实际上它是*仅*可用于桌面应用。  
  
 假设探查器 UI 编写为 C# yses 中的桌面应用的以下 ode 示例`PackageManager`生成 Windows 应用的列表：  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **指定的自定义环境块**  
 新的 COM 接口， [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)，允许你自定义用于简化某些形式的诊断的 Windows 应用商店应用的执行行为。  其方法之一[EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx)，可以将环境块传递给 Windows 应用商店应用中，当启动它时，以及其他有用的效果，例如禁用自动过程挂起。  环境块很重要，因为这是你需要指定环境变量 (`COR_PROFILER`， `COR_ENABLE_PROFILING`，和`COR_PROFILER_PATH)`) CLR 用于加载探查器 DLL。  
  
 请考虑下面的代码段：  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 有几个需要正确的项：  
  
-   `packageFullName` 可以同时遍历包并抓取确定`package.Id.FullName`。  
  
-   `debuggerCommandLine` 较之前更有趣的是。  若要将自定义环境块传递给 Windows 应用商店应用，你需要编写你自己，简单的 dummy 调试器。  Windows spawns Windows 应用商店应用程序挂起，然后将调试器附加通过启动与如下在此示例中的命令行调试程序：  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     其中`-p 1336`意味着 Windows 应用商店应用具有进程 ID 1336 和`-tid 1424`意味着线程 ID 1424 是挂起的线程。  Dummy 调试器将分析从命令行的 ThreadID、 恢复该线程，然后退出。  
  
     下面是一些示例来执行此操作的 c + + 代码 （请务必添加错误检查 ！）：  
  
    ```cpp  
    int wmain(int argc, wchar_t* argv[])  
    {      
        // …  
        // Parse command line here  
        // …  
  
        HANDLE hThread = OpenThread(THREAD_SUSPEND_RESUME,   
                                                                  FALSE /* bInheritHandle */, nThreadID);  
        ResumeThread(hThread);  
        CloseHandle(hThread);  
        return 0;  
    }  
    ```  
  
     你将需要将此 dummy 调试器部署为诊断工具安装，过程中，然后指定此调试器中的路径`debuggerCommandLine`参数。  
  
 **启动 Windows 应用商店应用**  
 最后到达时间以启动 Windows 应用商店应用程序。 如果你已已尝试过执行自己，你可能已经注意到， [CreateProcess](https://msdn.microsoft.com/library/windows/desktop/ms682425\(v=vs.85\).aspx)是不如何创建 Windows 应用商店应用过程。  相反，你将需要使用[IApplicationActivationManager::ActivateApplication](https://msdn.microsoft.com/library/windows/desktop/Hh706903\(v=vs.85\).aspx)方法。  若要做到这一点，你将需要获取正在启动 Windows 应用商店应用的应用程序用户模型 ID。  并且，这意味着你将需要执行少量寻找通过清单。  
  
 循环访问你的包裹时 (请参阅中的"选择 Windows 应用商店应用程序到配置文件"[启动负载](#Startup)前面部分)，你将需要获取的当前包清单中包含的应用程序集：  
  
```csharp  
string manifestPath = package.InstalledLocation.Path + "\\AppxManifest.xml";  
  
AppxPackaging.IStream manifestStream;  
SHCreateStreamOnFileEx(  
                    manifestPath,  
                    0x00000040,     // STGM_READ | STGM_SHARE_DENY_NONE  
                    0,              // file creation attributes  
                    false,          // fCreate  
                    null,           // reserved  
                    out manifestStream);  
  
IAppxManifestReader manifestReader = appxFactory.CreateManifestReader(manifestStream);  
  
IAppxManifestApplicationsEnumerator appsEnum = manifestReader.GetApplications();  
```  
  
 是，一个包可以有多个应用程序，并且每个应用程序具有其自己的应用程序用户模型 id。  因此你将想要提出你的用户的应用程序到配置文件，并获取来自该特定应用程序的应用程序用户模型 ID:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
…  
```  
  
 最后，你现在有你需要启动 Windows 应用商店应用：  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **请记住要调用 DisableDebugging**  
 当调用[IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx)，你所做的一个承诺，你将在后清理自己通过调用[IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx)方法，因此请确保不要分析会话时通过。  
  
<a name="Attach"></a>   
### <a name="attach-load"></a>附加负载  
 当你的探查器 UI 想要将其探查器 DLL 附加到的应用程序已经启动了运行时，它会使用[iclrprofiling:: Attachprofiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)。  同样适用于 Windows 应用商店应用。  但除了前面列出的常见注意事项，请确保目标 Windows 应用商店应用程序则不会挂起。  
  
 **EnableDebugging**  
 启动负载，使用调用[IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx)方法。  你不需要它传递到环境块中，但你需要它的其他功能之一： 禁用自动过程挂起。  否则为当你的探查器 UI 调用[AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md)，目标 Windows 应用商店应用程序可能会挂起。  事实上，这可能是如果用户现在交互你探查器用户界面时，以及 Windows 应用商店应用程序未在任何用户的屏幕上处于活动状态。  如果 Windows 应用商店应用已挂起，它也不能以响应任何发出信号，CLR 将发送到它附加探查器 DLL。  
  
 因此你将想要这样做：  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */,   
                                                                 IntPtr.Zero /* environment */);  
```  
  
 这是相同的调用会启动加载的情况下，为使的但未指定调试器命令行或环境块。  
  
 **DisableDebugging**  
 与往常一样，不要忘记将调用[IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx)完成时，将分析会话。  
  
<a name="Running"></a>   
## <a name="running-inside-the-windows-store-app"></a>在 Windows 应用商店应用程序内部运行  
 因此 Windows 应用商店应用最后加载探查器 DLL。  现在必须让探查器 DLL 如何播放所需的 Windows 应用商店应用的不同规则，包括允许哪些 Api 以及如何使用运行较少的权限。  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>停在 Windows 应用商店应用程序 Api  
 当您浏览 Windows API，你会注意到为适用于桌面应用、 Windows 应用商店应用，或同时记录了每个 API。  例如，**要求**一部分的文档[InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx)函数指示该函数，适用于桌面应用程序。 与此相反， [InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx)函数是可用于桌面应用和 Windows 应用商店应用。  
  
 在开发时探查器 DLL，则将它视为它是一个 Windows 应用商店应用，并且仅使用进行了说明为可供 Windows 应用商店应用的 Api。  分析依赖项 (例如，你可以运行`link /dump /imports`针对你要审核的探查器 DLL)，然后搜索文档以查看哪些依赖项是确定，这不是。  在大多数情况下，可通过只需将其替换为安全记录的 API 的较新窗体解决你冲突 (例如，替换[InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx)与[InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx))。  
  
 你可能注意到，探查器 DLL 调用适用于仅，桌面应用的一些 Api，并且尚未它们看起来像是工作即使探查器 DLL 加载内的 Windows 应用商店应用。  请注意，它将使用未记录在探查器 DLL 时加载到 Windows 应用商店应用程序进程中的 Windows 应用商店应用使用任何 API 的风险：  
  
-   若要在 Windows 应用商店应用中运行的唯一上下文中调用时，不保证都类 Api。  
  
-   当在不同的 Windows 应用商店应用程序进程内从调用时，此类 Api 可能不一致地工作。  
  
-   此类 Api 可能看起来不错，从 Windows 应用商店应用中的当前版本的 Windows 中，但可能会中断或禁用 Windows 的将来版本中。  
  
 最好的建议是解决所有冲突并避免风险。  
  
 你可能会发现你绝对不能缺少特定的 API 和找不到替代适用于 Windows 应用商店应用。  在这种情况下，一项基本要求：  
  
-   测试、 测试、 测试动态 daylights 超出该 API 的使用情况。  
  
-   了解 API 可能会突然中断或消失如果调用从在 Windows 应用商店应用在将来的版本的 Windows。  这不会由 Microsoft、 视为兼容性问题和支持它的使用情况将不会优先级。  
  
<a name="Permissions"></a>   
### <a name="reduced-permissions"></a>降低的权限  
 它不在本主题列出 Windows 应用商店应用程序权限不同于桌面应用的所有方法的范围。  但肯定行为将是不同每次探查器 DLL （时加载到相比桌面应用程序的 Windows 应用商店应用） 尝试访问的任何资源。  文件系统是最常见的示例。  有但是少数将放置在给定的 Windows 应用商店应用允许访问的磁盘 (请参阅[文件访问和权限 (Windows 运行时应用](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx))，并且探查器 DLL 将在相同的限制。  应彻底测试你的代码。  
  
<a name="Interprocess"></a>   
### <a name="inter-process-communication"></a>进程间通信  
 本白皮书开头图中所示，探查器 DLL （加载到 Windows 应用商店应用程序进程空间） 可能需要与你探查器的 UI （在单独的桌面应用程序进程空间中运行） 通过自定义的间流程通信通信 (IPC) 通道。  探查器用户界面将信号发送到探查器 DLL 以修改其行为和探查器 DLL 将数据从经过分析的 Windows 应用商店应用发送回用于操作的后续处理和向探查器用户显示的事件探查器 UI。  
  
 大多数探查器需要处理这种方式，但在探查器 DLL 加载到 Windows 应用商店应用时，您为 IPC 机制的选择会限制更多。  例如，命名的管道不属于 Windows 应用商店应用程序 SDK，因此不能使用它们。  
  
 但是当然，文件仍在中，但在更多限制的方式。  此外，还提供事件。  
  
 **通过文件进行通信**  
 你的大多数数据将通过文件可能传入探查器 DLL 和探查器用户界面之间。  关键是要选取文件位置，你 （在 Windows 应用商店应用的上下文中） 的探查器 DLL 和探查器 UI 具有读取和写入访问权限。  例如，临时文件夹的路径是可以访问你的探查器 DLL 和探查器用户界面的位置，但没有其他 Windows 应用商店应用程序包可以访问 （因此屏蔽日志从其他 Windows 应用商店应用程序包的任何信息）。  
  
 你的探查器用户界面和探查器 DLL 可以独立地确定此路径。  探查器 UI，在该示例循环访问当前用户安装的所有包时 （请参阅前面的示例代码），都可访问`PackageId`类，可以从中派生的临时文件夹路径类似于此代码段的代码。  （与往常一样，错误检查省略了为简洁起见。）  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 同时，探查器 DLL 可以执行基本上相同的操作，但它可以更多轻松获取到[ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx)类通过[ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx)属性。  
  
 **通过事件进行通信**  
 如果你想探查器用户界面和探查器 DLL 之间的简单信号语义，可以使用 Windows 应用商店应用以及桌面应用中的事件。  
  
 从探查器 DLL，只需调用[CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx)函数来创建的命名的事件与你喜欢的任何名称。  例如：  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 然后需要查找 Windows 应用商店应用程序的命名空间下该命名的事件探查器用户界面。  例如，可以调用你的探查器 UI [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx)，指定形式的事件名称  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>` 为 Windows 应用商店应用的 AppContainer SID。  本主题前面部分介绍了如何循环访问当前用户安装的包。  从该示例代码，你可以获取 packageId。  并从 packageId，可以获取`<acSid>`类似以下的代码：  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
<a name="Shutdown"></a>   
### <a name="no-shutdown-notifications"></a>没有关闭通知  
 当运行在 Windows 应用商店应用时，探查器 DLL 不应依赖于任一[icorprofilercallback:: Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)甚至[DllMain](https://msdn.microsoft.com/library/windows/desktop/ms682583\(v=vs.85\).aspx) (与`DLL_PROCESS_DETACH`) 正在调用以通知探查器 DLL正在退出 Windows 应用商店应用。  事实上，可以预见永远不会调用。  从历史上看，许多探查器 Dll 将用作这些通知方便的位置以刷新缓存到磁盘、 关闭文件中，将通知发送回探查器用户界面，等等。但现在需要略有不同组织探查器 DLL。  
  
 探查器 DLL，因为它将应日志记录信息。  出于性能原因，你可能想要批处理内存中的信息，然后刷新到磁盘随着批处理中过去的某一阈值的大小的增长。  但假定尚未被刷新到磁盘的任何信息可能会丢失。  这意味着你将想要这样做是明智，选取你阈值和探查器 UI，需要强制写入处理编写的探查器 DLL 的信息不完整。  
  
<a name="Metadata"></a>   
## <a name="windows-runtime-metadata-files"></a>Windows 运行时元数据文件  
 它是深入介绍本文档的作用域之外哪些 Windows 运行时元数据 (WinMD) 文件。    本部分仅限于 CLR 分析 API 在 WinMD 文件加载的探查器 DLL 在分析 Windows 应用商店应用程序时的反应。  
  
<a name="WMDs"></a>   
### <a name="managed-and-non-managed-winmds"></a>托管和非托管 Winmd  
 如果开发人员使用 Visual Studio 创建新的 Windows 运行时组件项目，生成该项目将生成 WinMD 文件描述由开发人员创作的元数据 （类、 接口、 等的类型说明）。  如果此项目是用 C# 或 VB 编写的托管的语言项目，该相同的 WinMD 文件还包含这些类型 （它包含所有源代码中的开发人员的代码编译的 IL 的含义） 的实现。  此类文件被称为托管 WinMD 文件。  这些更改将有趣的因为它们包含 Windows 运行时元数据和基础的实现。  
  
 与此相反，如果开发人员为 c + + 创建 Windows 运行时组件项目，该项目的生成过程生成的 WinMD 文件只包含元数据，并实现会编译成单独的本机 DLL。  同样，在 Windows SDK 中提供的 WinMD 文件包含只有元数据，与编译成单独随附的 Windows 的本机 Dll 的实现。  
  
 下面的信息适用于这两个托管的 Winmd，其中包含元数据和实现，和到非托管 Winmd，其中包含仅元数据。  
  
<a name="CLRModules"></a>   
### <a name="winmd-files-look-like-clr-modules"></a>WinMD 文件如下所示的 CLR 模块  
 就 CLR 而言，所有 WinMD 文件都是模块。  CLR 分析 API 因此通知探查器 DLL 时 WinMD 文件加载和其 ModuleIDs 是什么，用于其他托管的模块的相同方式。  
  
 探查器 DLL 可以通过调用从其他模块区分 WinMD 文件[icorprofilerinfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)方法并检查`pdwModuleFlags`输出参数[COR_PRF_MODULE_WINDOWS_运行时](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)标志。  （是设置当且仅当 ModuleID 表示 WinMD。）  
  
<a name="Reading"></a>   
### <a name="reading-metadata-from-winmds"></a>从 Winmd 读取元数据  
 WinMD 文件，类似于正则模块包含元数据，可以通过读取[元数据 Api](../../../../docs/framework/unmanaged-api/metadata/index.md)。  但是，CLR 将 Windows 运行时类型到.NET Framework 类型时它读取 WinMD 文件，以便开发人员程序在托管代码和使用的 WinMD 文件可以具有更自然的编程体验。  这些映射的一些示例，请参阅[.NET Framework 支持 Windows 应用商店应用和 Windows 运行时](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)。  
  
 因此哪种视图探查器时，将看到它使用 Api 的元数据： 原始的 Windows 运行时视图中或映射的.NET Framework 视图？  答案： 完全取决于您。  
  
 当调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)方法 WinMD 获取元数据接口，如[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)，你可以选择设置[ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)中`dwOpenFlags`参数来关闭此映射。  否则，默认情况下，将启用映射。  通常，探查器将保留启用的映射，以便熟悉而自然向探查器用户将查找探查器 DLL 中获取的 WinMD 元数据 （例如，名称的类型） 的字符串。  
  
<a name="Modifying"></a>   
### <a name="modifying-metadata-from-winmds"></a>修改从 Winmd 元数据  
 不支持修改中 Winmd 元数据。  如果调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)方法 WinMD 文件，并指定[ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)中`dwOpenFlags`参数或如寻求可写元数据接口[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)， [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)将失败。  这一点 IL 重写的探查器需要修改元数据以支持 （例如，若要添加 AssemblyRefs 或新的方法） 其检测到的特定非常重要。  因此你应该检查的[COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)首先 （如在上一节中讨论） 和避免在此类模块要求提供可写元数据接口。  
  
<a name="Resolving"></a>   
### <a name="resolving-assembly-references-with-winmds"></a>解决与 Winmd 的程序集引用  
 对于许多探查器需要解析元数据引用手动以帮助检测或类型检查。  此类探查器需要注意的 CLR 如何解析指向 Winmd 的程序集引用，因为与标准程序集的引用完全不同的方式解析这些引用。  
  
<a name="Profilers"></a>   
## <a name="memory-profilers"></a>内存探查器  
 垃圾回收器和托管的堆不完全不同的 Windows 应用商店应用和桌面应用程序中。  但是，有探查器作者需要注意的一些细微的差异。  
  
<a name="ForceGC"></a>   
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC 创建一个托管的线程  
 在执行内存分析时，探查器 DLL 通常会创建一个独立于其调用线程[ForceGC 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)方法。  这是什么新鲜事物。  但有可能是什么令人惊讶的执行垃圾回收中的 Windows 应用商店应用的行为可能将你的线程转换为托管线程 （例如，分析 API ThreadID 将为创建该线程）。  
  
 若要了解此后果，务必了解 CLR 分析 API 定义的同步和异步调用之间的差异。 请注意，这是非常不同于 Windows 应用商店应用中的异步调用的概念。  请参阅博客文章[我们使用 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/)有关详细信息。  
  
 相关点是，在由你的探查器创建的线程上所做的调用始终被视为同步，即使这些调用来自外部的探查器 DLL 的之一实现[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)方法。  至少，用于以出现这种情况。  现在，CLR 已启用探查器的线程到托管线程因你调用[ForceGC 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)，线程将不再被视为探查器的线程。  在这种情况下，CLR 强制实施更严格定义的什么限定为该线程的同步-即，调用都必须源自在探查器 DLL 的之一[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)限定为同步的方法。  
  
 在实践中，这意味着什么？  大多数[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)方法是仅安全同步，调用的否则将立即失败。  因此，如果探查器 DLL 重复使用你[ForceGC 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)通常在探查器所创建的线程上进行其他调用的线程 (例如，若要[RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)， [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)，或[RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md))，你要时遇到问题。  即使如异步安全函数[DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)具有从托管线程中调用时的特殊规则。 (请参阅博客文章[探查器堆栈审核： 基础知识和场外](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/)有关详细信息。)  
  
 因此，我们建议，探查器 DLL 创建，以便在调用任何线程[ForceGC 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)应使用*仅*为了触发 Gc，然后响应 GC 回调。  它不应调用到要执行其他任务，例如堆栈采样或分离的分析 API。  
  
<a name="WeakTable"></a>   
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences  
 从.NET Framework 4.5 开始，没有新的 GC 回调， [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)，探查器有关的更完整信息其中给出了*依赖句柄*。 这些句柄有效地将引用从的源对象添加到为了进行 GC 生存期管理的目标对象。  依赖句柄是否新鲜，并且开发人员，在托管代码中编程已能够通过创建自己依赖句柄<xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType>之前 Windows 8 和.NET Framework 4.5 的类。  
  
 但是，现在托管的 XAML Windows 应用商店应用，请使用大量的相关句柄。  具体而言，CLR 使用它们来帮助管理托管的对象和非托管的 Windows 运行时对象之间的引用周期。  这意味着，更重要的是现在比前所未有的内存探查器，以获悉的这些依赖句柄，以便它们可以可视化的其余部分堆关系图中的边缘。  应使用探查器 DLL [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)， [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)，和[ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)在一起以形成一个完整的堆关系图视图.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>结束语  
 它是可以使用 CLR 分析 API 来分析 Windows 应用商店应用中运行的托管的代码。  事实上，可以执行你正在开发的现有探查器，并进行一些特定的更改，以便它可以面向 Windows 应用商店应用。   探查器 UI 应使用新的 Api 进行激活 Windows 应用商店应用程序在调试模式下。  请确保： 探查器 DLL 所消耗的仅适用于 Windows 应用商店应用的 Api。  记住的 Windows 应用商店应用 API 限制和受限的权限，在 Windows 应用商店应用的位置的大致认知，应编写你的探查器 DLL 和探查器用户界面之间的通信机制。  应注意如何则 CLR 会将 Winmd，探查器 DLL 和垃圾回收器的行为是与托管线程不同的方式。  
  
<a name="Resources"></a>   
## <a name="resources"></a>资源  
 **公共语言运行时**  
 -   [CLR 分析 API 参考](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [CLR 元数据 API 参考](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **与 Windows 运行时的 CLR 的交互**  
 [.NET Framework 对 Windows 应用商店应用和 Windows 运行时的支持情况](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
  
 **Windows 应用商店应用**  
 -   [文件访问和权限 （Windows 运行时应用](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [获取开发人员许可证](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [IPackageDebugSettings 接口](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>请参阅  
 [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
