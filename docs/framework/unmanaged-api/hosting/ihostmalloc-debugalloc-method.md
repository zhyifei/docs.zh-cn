---
title: IHostMAlloc::DebugAlloc 方法
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178040"
---
# <a name="ihostmallocdebugalloc-method"></a>IHostMAlloc::DebugAlloc 方法
请求主机从堆中分配指定数量的内存，并另外跟踪内存的分配位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a>parameters  
 `cbSize`  
 [在]当前内存分配请求的大小（以字节为单位）。  
  
 `dwCriticalLevel`  
 [在][EMemory临界级别值](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md)之一，指示分配失败的影响。  
  
 `pszFileName`  
 [在]正在调试的可执行文件的代码文件。  
  
 `iLineNo`  
 [在]请求分配`pszFileName`中的行号。  
  
 `ppMem`  
 [出]指向已分配的内存的指针，如果无法完成请求，则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|说明|  
|-------------|-----------------|  
|S_OK|`DebugAlloc`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或者 CLR 处于无法成功运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|呼叫超时。|  
|HOST_E_NOT_OWNER|调用方不拥有锁。|  
|HOST_E_ABANDONED|当阻塞的线程或光纤等待事件时，事件已被取消。|  
|E_FAIL|发生了未知的灾难性故障。 当方法返回E_FAIL时，CLR 在进程中不再可用。 对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。|  
|E_OUTOFMEMORY|没有足够的内存来完成分配请求。|  
  
## <a name="remarks"></a>备注  
 CLR 通过调用[IHostMemoryManagerManager：：createMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法获取指向[IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)实例的接口指针。 `DebugAlloc`允许运行时获取代码文件信息，供调试期间使用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** 作为资源包含在 MSCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [IHostMalloc 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
