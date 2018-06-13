---
title: 弃用的 CLR 承载函数
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d86f9b4903663604094895f6747b1407ff98c990
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435859"
---
# <a name="deprecated-clr-hosting-functions"></a>弃用的 CLR 承载函数
本部分介绍的托管 API 的早期版本使用的非托管全局静态函数。  
  
 除了基础结构函数 (`_Cor*`函数)，用于仅由.NET Framework，这些函数中已弃用[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。  
  
## <a name="activation-functions"></a>激活函数  
 [ClrCreateManagedInstance 函数](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 已否决。 创建指定的托管类型的实例。  
  
 [CoInitializeCor 函数](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 已过时。 若要初始化公共语言运行时 (CLR)，使用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)。  
  
 [CoInitializeEE 函数](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 已否决。 确保 CLR 执行引擎已加载到进程。 使用[iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法相反。  
  
 [CorBindToCurrentRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 已否决。 通过使用版本信息存储在 XML 文件中，到的进程中加载公共语言运行时 (CLR)。  
  
 [CorBindToRuntime 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 已否决。 使非托管的宿主能够将 CLR 加载到过程中。  
  
 [CorBindToRuntimeByCfg 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 已否决。 通过使用从 XML 文件中读取的版本信息加载到进程的 CLR。  
  
 [CorBindToRuntimeEx 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 已否决。 提供非托管的宿主能够将 CLR 加载到进程中，并允许你设置标志以指定的 CLR 的行为。  
  
 [CorBindToRuntimeHost 函数](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 已否决。 使主机可以加载到进程的 CLR 的指定的版本。  
  
 [GetCORRequiredVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 已否决。 获取所需的 CLR 版本数量。  
  
 [GetCORSystemDirectory 函数](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 已否决。 返回加载到进程的 CLR 的安装目录。  
  
 [GetRealProcAddress 函数](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 已否决。 获取指定从最新的已安装的 CLR 版本导出的函数的地址。  
  
 [GetRequestedRuntimeInfo 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 已否决。 获取有关应用程序请求的 CLR 版本和目录信息。  
  
## <a name="clr-version-functions"></a>CLR 版本函数  
 本部分中的函数返回的 CLR 版本;它们不激活 CLR。  
  
 [GetCORVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 已否决。 返回在当前进程中运行 CLR 的版本号。  
  
 [GetFileVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 已否决。 获取指定的文件，使用指定的缓冲区的 CLR 版本信息。  
  
 [GetRequestedRuntimeVersion 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 已否决。 获取由指定的应用程序请求的 CLR 的版本号。 如果未安装该版本，获取在请求的版本之前安装了最新版本。  
  
 [GetRequestedRuntimeVersionForCLSID 函数](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 已否决。 获取具有指定的 CLSID 的类的相应 CLR 版本信息。  
  
 [GetVersionFromProcess 函数](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 已否决。 获取与指定的进程句柄关联的 CLR 的版本号。  
  
 [LockClrVersion 函数](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 已否决。 允许宿主确定在进行显式初始化 CLR 之前将在过程内使用 CLR 的版本。  
  
## <a name="hosting-functions"></a>承载函数  
 [CallFunctionShim 函数](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 已否决。 将指定的库中具有指定的名称和参数的函数调用。  
  
 [CoEEShutDownCOM 函数](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 已否决。 卸载过程中的 COM 程序集。  
  
 [CorExitProcess 函数](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 已否决。 关闭当前的非托管进程。  
  
 [CorLaunchApplication 函数](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 已否决。 启动位于指定的网络路径，使用指定的清单和其他应用程序数据的应用程序。  
  
 [CorMarkThreadInThreadPool 函数](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 已否决。 将标记为托管代码的执行当前正在执行的线程池线程。 从.NET Framework 2.0 版开始，此函数不起作用。 它不是必需的并且可以在代码中删除。  
  
 [CoUninitializeCor 函数](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 已过时。 CLR 不能为从进程中卸载。  
  
 [CoUninitializeEE 函数](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 已过时。  
  
 [CreateDebuggingInterfaceFromVersion 函数](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 已否决。 创建[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象根据指定的版本信息。  
  
 [CreateICeeFileGen 函数](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 已否决。 创建[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。  
  
 [DestroyICeeFileGen 函数](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 已否决。 销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。  
  
 [FExecuteInAppDomainCallback 函数指针](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 已否决。 指向 CLR 调用以执行托管的代码的函数。  
  
 [FLockClrVersionCallback 函数指针](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 已否决。 指向 CLR 调用用于通知宿主的函数初始化已开始或完成。  
  
 [GetCLRIdentityManager 函数](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 已否决。 获取一个指针指向使 CLR 管理标识的接口。  
  
 [LoadLibraryShim 函数](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 已否决。 加载.NET Framework DLL 的指定的版本。  
  
 [LoadStringRC 函数](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 已否决。 将 HRESULT 值转换为一条错误消息中，通过使用当前线程的默认区域性。  
  
 [LoadStringRCEx 函数](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 已否决。 将转换为相应的错误消息为指定的区域性的 HRESULT 值。  
  
 [LPOVERLAPPED_COMPLETION_ROUTINE 函数指针](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 已否决。 指向通知时的重叠的宿主的函数 (即异步) 对设备 i/o 操作已完成。  
  
 [LPTHREAD_START_ROUTINE 函数指针](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 已否决。 指向通知线程已开始执行的主机的函数。  
  
 [RunDll32ShimW 函数](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 已否决。 执行指定的命令。  
  
 [WAITORTIMERCALLBACK 函数指针](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 已否决。 指向以通知主机，等待句柄已发出信号或超时的函数。  
  
## <a name="infrastructure-functions"></a>基础结构函数  
 本部分中的函数可由.NET Framework 仅使用。  
  
 [_CorDllMain 函数](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 初始化 CLR、 查找托管的入口点 DLL 程序集的 CLR 头中，并开始执行。  
  
 [_CorExeMain 函数](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 初始化 CLR，查找可执行程序集的 CLR 标头中的托管的入口点并开始执行。  
  
 [_CorExeMain2 函数](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 在指定的内存映射代码中执行的入口点。 操作系统加载程序通过调用此函数。  
  
 [_CorImageUnloading 函数](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 卸载托管的模块映像时通知加载程序。  
  
 [_CorValidateImage 函数](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 验证托管的模块映像，并通知操作系统加载程序后将其加载。  
  
## <a name="see-also"></a>请参阅  
 [.NET Framework 4 承载全局静态函数](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
