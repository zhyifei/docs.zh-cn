---
title: .NET Framework 4 和 4.5 中添加的 CLR 承载接口
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: a524c0b0e01fbde95ce2341874511960b3e5738e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616848"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="7d844-102">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="7d844-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="7d844-103">本节介绍了非托管主机可用于将 .NET Framework 4、.NET Framework 4.5 及更高版本中的公共语言运行时（CLR）集成到其应用程序中的接口。</span><span class="sxs-lookup"><span data-stu-id="7d844-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework 4, .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="7d844-104">这些接口为主机提供用于配置运行时并将其加载到进程中的方法。</span><span class="sxs-lookup"><span data-stu-id="7d844-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="7d844-105">从 .NET Framework 4 开始，所有宿主接口都具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="7d844-105">Starting with the .NET Framework 4, all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="7d844-106">它们使用生存期管理（ `AddRef` 和 `Release` ）、封装（隐式上下文）和 `QueryInterface` COM。</span><span class="sxs-lookup"><span data-stu-id="7d844-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="7d844-107">它们不使用 COM 类型 `BSTR` ，如、 `SAFEARRAY` 或 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="7d844-107">They do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="7d844-108">没有使用[CoCreateInstance 函数](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)的单元模型、聚合或注册表激活。</span><span class="sxs-lookup"><span data-stu-id="7d844-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d844-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="7d844-109">In This Section</span></span>  
 [<span data-ttu-id="7d844-110">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-110">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="7d844-111">提供检查应用程序域的内存和 CPU 使用情况的方法。</span><span class="sxs-lookup"><span data-stu-id="7d844-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="7d844-112">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-112">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)  
 <span data-ttu-id="7d844-113">使宿主能够指定将用于初始化默认应用程序域的应用程序域管理器，并指定初始化属性。</span><span class="sxs-lookup"><span data-stu-id="7d844-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="7d844-114">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-114">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)  
 <span data-ttu-id="7d844-115">提供[SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md)方法，该方法允许主机将垃圾回收段的大小和垃圾回收系统的第0代的最大大小设置为大于的值 `DWORD` 。</span><span class="sxs-lookup"><span data-stu-id="7d844-115">Provides the [SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="7d844-116">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-116">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)  
 <span data-ttu-id="7d844-117">提供一些方法，这些方法可返回 CLR 的特定版本，列出所有已安装的 Clr，列出所有进程内运行时，返回激活接口，并发现编译程序集所用的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="7d844-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="7d844-118">ICLRMetaHostPolicy 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-118">ICLRMetaHostPolicy Interface</span></span>](iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="7d844-119">提供[GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md)方法，该方法基于策略条件、托管程序集、版本和配置文件提供 CLR 接口。</span><span class="sxs-lookup"><span data-stu-id="7d844-119">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="7d844-120">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-120">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)  
 <span data-ttu-id="7d844-121">提供返回有关特定运行时的信息的方法，包括版本、目录和加载状态。</span><span class="sxs-lookup"><span data-stu-id="7d844-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="7d844-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)  
 <span data-ttu-id="7d844-123">提供用于对具有强名称的程序集进行签名的基本全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="7d844-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="7d844-124">所有[ICLRStrongName](iclrstrongname-interface.md)方法都返回标准 COM hresult。</span><span class="sxs-lookup"><span data-stu-id="7d844-124">All the [ICLRStrongName](iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="7d844-125">ICLRStrongName2 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-125">ICLRStrongName2 Interface</span></span>](iclrstrongname2-interface.md)  
 <span data-ttu-id="7d844-126">提供使用 SHA-1 安全哈希算法（SHA-256、SHA-384 和 SHA-512）组创建强名称的功能。</span><span class="sxs-lookup"><span data-stu-id="7d844-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="7d844-127">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="7d844-127">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)  
 <span data-ttu-id="7d844-128">提供[ICLRTask 接口](iclrtask-interface.md)的所有功能;此外，还提供了允许线程中止在当前线程上延迟的方法。</span><span class="sxs-lookup"><span data-stu-id="7d844-128">Provides all the functionality of the [ICLRTask Interface](iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7d844-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="7d844-129">Related Sections</span></span>  
 [<span data-ttu-id="7d844-130">弃用的 CLR 承载接口和 Coclass</span><span class="sxs-lookup"><span data-stu-id="7d844-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="7d844-131">介绍 .NET Framework 版本1.0 和1.1 随附的托管接口。</span><span class="sxs-lookup"><span data-stu-id="7d844-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="7d844-132">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="7d844-132">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="7d844-133">描述随 .NET Framework 版本2.0、3.0 和3.5 一起提供的托管接口。</span><span class="sxs-lookup"><span data-stu-id="7d844-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="7d844-134">承载</span><span class="sxs-lookup"><span data-stu-id="7d844-134">Hosting</span></span>](index.md)  
 <span data-ttu-id="7d844-135">介绍 .NET Framework 中的托管。</span><span class="sxs-lookup"><span data-stu-id="7d844-135">Introduces hosting in the .NET Framework.</span></span>
