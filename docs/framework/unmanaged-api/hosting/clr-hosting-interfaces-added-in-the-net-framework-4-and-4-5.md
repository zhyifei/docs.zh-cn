---
title: ".NET Framework 4 和 4.5 中添加的 CLR 承载接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61231715a24978e7fe57b2c9e87e7968dc0fdbc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>.NET Framework 4 和 4.5 中添加的 CLR 承载接口
本节描述非托管的接口主机可用于将公共语言运行时 (CLR) 集成在[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]， [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]，以及到其应用程序的更高版本。 这些接口提供的主机配置和运行时加载到进程的方法。  
  
 从开始[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]，所有托管接口具有以下特征：  
  
-   它们使用生命期管理 (`AddRef`和`Release`)，封装 （隐式上下文） 和`QueryInterface`从 com。  
  
-   存在不要使用 COM 类型，如`BSTR`， `SAFEARRAY`，或`VARIANT`。  
  
-   不没有使用任何单元模型、 聚合或注册表激活[CoCreateInstance 函数](http://go.microsoft.com/fwlink/?LinkId=142894)。  
  
## <a name="in-this-section"></a>本节内容  
 [ICLRAppDomainResourceMonitor 接口](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 提供检查应用程序域的内存和 CPU 使用率的方法。  
  
 [ICLRDomainManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 使主机可以指定将用于初始化默认应用程序域，以及指定初始化属性的应用程序域管理器。  
  
 [ICLRGCManager2 接口](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 提供[SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)方法，使主机可以设置为值的垃圾回收段的大小和第 0 代垃圾回收系统的最大大小大于`DWORD`。  
  
 [ICLRMetaHost 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 提供返回 CLR 的特定版本、 列出所有已安装的 Clr、 列出所有进程内运行时、 返回激活界面、 和发现用于编译的程序集的 CLR 版本的方法。  
  
 [ICLRMetaHostPolicy 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 提供[GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)提供 CLR 接口的方法基于策略条件、 托管程序集、 版本和配置文件。  
  
 [ICLRRuntimeInfo 接口](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 提供返回有关特定的运行库，包括版本、 目录和负载状态信息的方法。  
  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 提供基本的全局静态函数签名具有强名称的程序集。 所有[ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)方法返回标准的 COM Hresult。  
  
 [ICLRStrongName2 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 提供创建使用安全哈希算法 （sha-256、 sha-384 和 sha-512） 的 sha-2 组的强名称的能力。  
  
 [ICLRTask2 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 提供的所有功能[ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); 此外，都提供允许线程中止延迟，可将当前线程上的方法。  
  
## <a name="related-sections"></a>相关章节  
 [弃用的 CLR 承接接口和组件类](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 描述.NET framework 1.0 和 1.1 版提供的托管接口。  
  
 [CLR Hosting 接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 描述提供的.NET Framework 版本 2.0、 3.0 和 3.5 的托管接口。  
  
 [承载](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 引入了在.NET Framework 中承载。
