---
title: .NET Framework 4 和 4.5 中添加的 CLR 承载接口
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 982f5780a40dd8cbce02ec33f7e6f77589cd3717
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435791"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="421c8-102">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="421c8-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="421c8-103">本节描述非托管的接口主机可用于将公共语言运行时 (CLR) 集成在[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]， [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，以及到其应用程序的更高版本。</span><span class="sxs-lookup"><span data-stu-id="421c8-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], and later versions into their applications.</span></span> <span data-ttu-id="421c8-104">这些接口提供的主机配置和运行时加载到进程的方法。</span><span class="sxs-lookup"><span data-stu-id="421c8-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="421c8-105">从开始[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]，所有托管接口具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="421c8-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
-   <span data-ttu-id="421c8-106">它们使用生命期管理 (`AddRef`和`Release`)，封装 （隐式上下文） 和`QueryInterface`从 com。</span><span class="sxs-lookup"><span data-stu-id="421c8-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
-   <span data-ttu-id="421c8-107">存在不要使用 COM 类型，如`BSTR`， `SAFEARRAY`，或`VARIANT`。</span><span class="sxs-lookup"><span data-stu-id="421c8-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
-   <span data-ttu-id="421c8-108">不没有使用任何单元模型、 聚合或注册表激活[CoCreateInstance 函数](http://go.microsoft.com/fwlink/?LinkId=142894)。</span><span class="sxs-lookup"><span data-stu-id="421c8-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](http://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="421c8-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="421c8-109">In This Section</span></span>  
 [<span data-ttu-id="421c8-110">ICLRAppDomainResourceMonitor 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="421c8-111">提供检查应用程序域的内存和 CPU 使用率的方法。</span><span class="sxs-lookup"><span data-stu-id="421c8-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="421c8-112">ICLRDomainManager 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="421c8-113">使主机可以指定将用于初始化默认应用程序域，以及指定初始化属性的应用程序域管理器。</span><span class="sxs-lookup"><span data-stu-id="421c8-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="421c8-114">ICLRGCManager2 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="421c8-115">提供[SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法，使主机可以设置为值的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小大于`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="421c8-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="421c8-116">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="421c8-117">提供返回 CLR 的特定版本、 列出所有已安装的 Clr、 列出所有进程内运行时、 返回激活界面、 和发现用于编译的程序集的 CLR 版本的方法。</span><span class="sxs-lookup"><span data-stu-id="421c8-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="421c8-118">ICLRMetaHostPolicy 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="421c8-119">提供[GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)提供 CLR 接口的方法基于策略条件、 托管程序集、 版本和配置文件。</span><span class="sxs-lookup"><span data-stu-id="421c8-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="421c8-120">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="421c8-121">提供返回有关特定的运行库，包括版本、 目录和负载状态信息的方法。</span><span class="sxs-lookup"><span data-stu-id="421c8-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="421c8-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="421c8-123">提供基本的全局静态函数签名具有强名称的程序集。</span><span class="sxs-lookup"><span data-stu-id="421c8-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="421c8-124">所有[ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)方法返回标准的 COM Hresult。</span><span class="sxs-lookup"><span data-stu-id="421c8-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="421c8-125">ICLRStrongName2 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="421c8-126">提供创建使用安全哈希算法 （sha-256、 sha-384 和 sha-512） 的 sha-2 组的强名称的能力。</span><span class="sxs-lookup"><span data-stu-id="421c8-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="421c8-127">ICLRTask2 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="421c8-128">提供的所有功能[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); 此外，都提供允许线程中止延迟，可将当前线程上的方法。</span><span class="sxs-lookup"><span data-stu-id="421c8-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="421c8-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="421c8-129">Related Sections</span></span>  
 [<span data-ttu-id="421c8-130">弃用的 CLR 承接接口和组件类</span><span class="sxs-lookup"><span data-stu-id="421c8-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="421c8-131">描述.NET framework 1.0 和 1.1 版提供的托管接口。</span><span class="sxs-lookup"><span data-stu-id="421c8-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="421c8-132">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="421c8-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="421c8-133">描述提供的.NET Framework 版本 2.0、 3.0 和 3.5 的托管接口。</span><span class="sxs-lookup"><span data-stu-id="421c8-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="421c8-134">承载</span><span class="sxs-lookup"><span data-stu-id="421c8-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="421c8-135">引入了在.NET Framework 中承载。</span><span class="sxs-lookup"><span data-stu-id="421c8-135">Introduces hosting in the .NET Framework.</span></span>
