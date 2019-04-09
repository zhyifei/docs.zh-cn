---
title: Silverlight 调试
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d20bc002e52c3c6a42b45c0d1c5d559e65dc52c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113693"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="47b19-102">Silverlight 调试</span><span class="sxs-lookup"><span data-stu-id="47b19-102">Silverlight Debugging</span></span>
<span data-ttu-id="47b19-103">本部分中的主题描述了公共语言运行时 (CLR) 提供用于支持调试在 Windows 操作系统或在 Macintosh 平台上运行的基于 Silverlight 的应用程序的环境和接口。</span><span class="sxs-lookup"><span data-stu-id="47b19-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="47b19-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="47b19-104">In This Section</span></span>  
 [<span data-ttu-id="47b19-105">EnumerateCLRs 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-105">EnumerateCLRs Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 <span data-ttu-id="47b19-106">提供枚举进程中 CLR 的机制。</span><span class="sxs-lookup"><span data-stu-id="47b19-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="47b19-107">CloseCLREnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-107">CloseCLREnumeration Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 <span data-ttu-id="47b19-108">关闭任何位于返回的句柄数组中的有效 CLR 继续启动事件[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)，并释放句柄和字符串路径数组的内存。</span><span class="sxs-lookup"><span data-stu-id="47b19-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="47b19-109">CreateCoreClrDebugTarget 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-109">CreateCoreClrDebugTarget Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="47b19-110">创建进程和运行时枚举的远程目标连接。</span><span class="sxs-lookup"><span data-stu-id="47b19-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="47b19-111">CreateCordbObject 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-111">CreateCordbObject Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 <span data-ttu-id="47b19-112">创建调试器界面，该界面提供用于实例化远程进程上托管的调试会话的功能。</span><span class="sxs-lookup"><span data-stu-id="47b19-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="47b19-113">CreateVersionStringFromModule 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-113">CreateVersionStringFromModule Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 <span data-ttu-id="47b19-114">从目标进程中的 CLR 路径创建版本字符串。</span><span class="sxs-lookup"><span data-stu-id="47b19-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="47b19-115">CreateDebuggingInterfaceFromVersion 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-115">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="47b19-116">接受从返回的 CLR 版本字符串[CreateVersionStringFromModule 函数](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)函数，并返回相应的调试器接口。</span><span class="sxs-lookup"><span data-stu-id="47b19-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="47b19-117">CoreClrDebugProcInfo 结构</span><span class="sxs-lookup"><span data-stu-id="47b19-117">CoreClrDebugProcInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="47b19-118">表示在远程计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="47b19-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="47b19-119">CoreClrDebugRuntimeInfo 结构</span><span class="sxs-lookup"><span data-stu-id="47b19-119">CoreClrDebugRuntimeInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="47b19-120">表示远程计算机进程中加载的 CLR 实例。</span><span class="sxs-lookup"><span data-stu-id="47b19-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="47b19-121">GetStartupNotificationEvent 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-121">GetStartupNotificationEvent Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 <span data-ttu-id="47b19-122">创建或打开一个事件句柄，由在指定目标进程中加载的公共语言运行时 (CLR) 对其发出信号。</span><span class="sxs-lookup"><span data-stu-id="47b19-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="47b19-123">ICoreClrDebugTarget 接口</span><span class="sxs-lookup"><span data-stu-id="47b19-123">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="47b19-124">创建进程和运行时枚举的远程目标连接。</span><span class="sxs-lookup"><span data-stu-id="47b19-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="47b19-125">InitDbgTransportManager 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-125">InitDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 <span data-ttu-id="47b19-126">初始化传输管理器以连接到进程和运行时枚举的远程目标。</span><span class="sxs-lookup"><span data-stu-id="47b19-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="47b19-127">ShutdownDbgTransportManager 函数</span><span class="sxs-lookup"><span data-stu-id="47b19-127">ShutdownDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="47b19-128">关闭用于远程目标计算机连接的传输管理器。</span><span class="sxs-lookup"><span data-stu-id="47b19-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b19-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="47b19-129">See also</span></span>

- [<span data-ttu-id="47b19-130">调试 Coclass</span><span class="sxs-lookup"><span data-stu-id="47b19-130">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)
- [<span data-ttu-id="47b19-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="47b19-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="47b19-132">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="47b19-132">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
- [<span data-ttu-id="47b19-133">调试枚举</span><span class="sxs-lookup"><span data-stu-id="47b19-133">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="47b19-134">调试结构</span><span class="sxs-lookup"><span data-stu-id="47b19-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
