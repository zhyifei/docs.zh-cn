---
title: IGCHost::GetThreadStats 方法
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87e318c4f2367e8c66910978f4a9c89f36c95632
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766518"
---
# <a name="igchostgetthreadstats-method"></a>IGCHost::GetThreadStats 方法
获取垃圾回收的每个线程统计信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>参数  
 `pFiberCookie`  
 [in]指定要为其检索统计信息的线程的纤程 cookie 指向的指针。  
  
 `pStats`  
 [in、 out]一个指向[COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)结构，其中包含指定的线程的垃圾收集统计信息。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl GCHost.h  
  
 **库：** 包含为 MSCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IGCHost 接口](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
