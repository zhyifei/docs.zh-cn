---
title: IHostMAlloc::Alloc 方法
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176300"
---
# <a name="ihostmallocalloc-method"></a>IHostMAlloc::Alloc 方法
请求主机从堆分配指定的内存量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a>parameters  
 `cbSize`  
 [在]当前内存分配请求的大小（以字节为单位）。  
  
 `dwCriticalLevel`  
 [在][EMemory临界级别值](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)之一，指示分配失败的影响。  
  
 `ppMem`  
 [出]指向已分配的内存的指针，如果无法完成请求，则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`Alloc`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|呼叫超时。|  
|HOST_E_NOT_OWNER|调用方不拥有锁。|  
|HOST_E_ABANDONED|当阻塞的线程或光纤等待事件时，事件已被取消。|  
|E_FAIL|发生了未知的灾难性故障。 当方法返回E_FAIL时，CLR 在进程中不再可用。 对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存来完成分配请求。|  
  
## <a name="remarks"></a>备注  
 CLR 通过调用`IHostMalloc`[IHostMemoryManager：：createMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法获取指向实例的接口指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
