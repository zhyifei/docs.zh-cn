---
title: IHostMemoryManager::GetMemoryLoad 方法
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176274"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>IHostMemoryManager::GetMemoryLoad 方法
获取主机报告当前正在使用且因此不可用的物理内存量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a>parameters  
 `pMemoryLoad`  
 [出]指向当前正在使用的总物理内存的近似百分比的指针。  
  
 `pAvailableBytes`  
 [出]指向公共语言运行时 （CLR） 可用的字节数的指针。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|呼叫超时。|  
|HOST_E_NOT_OWNER|调用方不拥有锁。|  
|HOST_E_ABANDONED|当阻塞的线程或光纤等待事件时，事件已被取消。|  
|E_FAIL|发生了未知的灾难性故障。 当方法返回E_FAIL时，CLR 在进程中不再可用。 对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。|  
  
## <a name="remarks"></a>备注  
 `GetMemoryLoad`包装 Win32`GlobalMemoryStatus`函数。 的值`pMemoryLoad`相当于从`dwMemoryLoad``MEMORYSTATUS``GlobalMemoryStatus`返回的结构中的字段。  
  
 运行时使用返回值作为垃圾回收器的启发式。 例如，如果主机报告大多数内存正在使用中，垃圾回收器可能会选择从多代收集，以增加可能可用的内存量。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.GC?displayProperty=nameWithType>
- [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
