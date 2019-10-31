---
title: EMemoryCriticalLevel 枚举
ms.date: 03/30/2017
api_name:
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
ms.openlocfilehash: 8364d38f7ab81b73fd8b47d2251bc0ff1b2c71e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138246"
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel 枚举
包含一些值，这些值指示在请求特定内存分配但无法满足时，失败所造成的影响。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`eAppDomainCritical`|指示分配对于在已请求分配的域中执行托管代码是至关重要的。 如果无法分配内存，则 CLR 无法保证域仍可用。 主机决定当无法满足分配时要执行的操作。 它可以指示 CLR 自动中止 `AppDomain`，或通过在[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)上调用方法来使其保持运行。|  
|`eProcessCritical`|指示分配对于进程中的托管代码执行至关重要。 此值在启动和运行终结器时使用。 如果无法分配内存，则 CLR 无法在进程中运行。 如果分配失败，则会有效地禁用 CLR。 对 CLR 的所有后续调用都将失败，并出现 HOST_E_CLRNOTAVAILABLE。|  
|`eTaskCritical`|指示分配对于运行已请求分配的任务至关重要。 如果无法分配内存，则 CLR 无法保证任务能够执行。 发生故障时，CLR 将在物理操作系统线程上引发 <xref:System.Threading.ThreadAbortException>。|  
  
## <a name="remarks"></a>备注  
 [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)和[IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)接口中定义的内存分配方法采用此类型的参数。 根据故障的严重性，主机可以决定是立即对分配请求进行故障转移还是要等待，直到它得以满足。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRMemoryNotificationCallback 接口](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [承载枚举](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
