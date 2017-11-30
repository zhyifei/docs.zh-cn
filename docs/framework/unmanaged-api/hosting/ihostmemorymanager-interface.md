---
title: "IHostMemoryManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 415539be0dbed8e0cf3f9d6e5c79bf4cfac09fe2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager 接口
提供允许公共语言运行时 (CLR) 可通过主机，虚拟内存请求的方法，而不是使用标准 Win32 虚拟内存函数。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|通知主机公共语言运行时 (CLR) 已获取从操作系统指定的内存。|  
|[CreateMAlloc 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|获取到的接口指针[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)用于从非回收堆由宿主创建请求的内存分配的实例。|  
|[GetMemoryLoad 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|报告的主机，请获取当前正在使用的物理内存量。|  
|[NeedsVirtualAddressSpace 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|通知宿主，CLR 将尝试使用指定的内存。|  
|[RegisterMemoryNotificationCallback 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|注册到主机时，将调用以通知在计算机上的当前内存加载的 CLR 的回调函数的指针。|  
|[ReleasedVirtualAddressSpace 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|通知主机 CLR 已结束使用指定的内存。|  
|[VirtualAlloc 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|用作的逻辑包装，相应的 Win32 函数，将保留或提交调用进程虚拟地址空间中的页面的区域。|  
|[VirtualFree 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|用作相应的 Win32 函数，该释放、 解除或释放和解除的调用进程的虚拟地址空间中的页区域函数的逻辑包装。|  
|[VirtualProtect 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|用作更改调用进程的虚拟地址空间中的提交页面的保护区域上的对应 Win32 函数的逻辑包装。|  
|[VirtualQuery 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|用作检索有关调用进程虚拟地址空间中的页面范围的信息的相应 Win32 函数的逻辑包装。|  
  
## <a name="remarks"></a>备注  
 `IHostMemoryManager`此外提供了方法，以便 CLR 获取通过其在堆上进行内存请求并获取在过程中，内存压力级别的指针，如报告的主机。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IHostMalloc 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
