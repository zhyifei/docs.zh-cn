---
title: "IHostMemoryManager::VirtualAlloc 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 761958c44ad374d522a52826929e320e65957ffa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualalloc-method"></a>IHostMemoryManager::VirtualAlloc 方法
用作相应的 Win32 函数的逻辑包装。 Win32 实现`VirtualAlloc`保留或提交调用进程虚拟地址空间中的页面的区域。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [in]指向要分配的区域的起始地址的指针。  
  
 `dwSize`  
 [in]以字节为单位的区域的大小。  
  
 `flAllocationType`  
 [in]内存分配的类型。  
  
 `flProtect`  
 [in]区域页，并将其分配的内存保护。  
  
 `dwCriticalLevel`  
 [in][EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)值，该值指示分配失败的影响。  
  
 `ppMem`  
 [out]指向分配的内存，则为 null，如果不能满足请求的起始地址的指针。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`VirtualAlloc`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存已可用于完成分配请求|  
  
## <a name="remarks"></a>备注  
 在你的过程的地址空间中调用保留区域`VirtualAlloc`。 `pAddress`参数包含所需的内存块的起始地址。 通常情况下设置此参数为 null。 操作系统将保留的可用地址范围可供你的过程的记录。 A `pAddress` null 值指示系统将保留区域，只要它认为合适。 或者，你可以为内存块提供特定的起始地址。 在这两种情况下，输出参数`ppMem`作为指针返回到分配的内存。 该函数本身返回的 HRESULT 值。  
  
 Win32`VirtualAlloc`函数没有`ppMem`参数，并改为返回指向分配的内存的指针。 有关详细信息，请参阅 Windows 平台文档。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
