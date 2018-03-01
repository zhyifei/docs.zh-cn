---
title: "ICorPublishProcess::EnumAppDomains 方法"
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
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 938c022788d5ed9f0e28f794432017748dc096e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessenumappdomains-method"></a>ICorPublishProcess::EnumAppDomains 方法
对于应用程序域引用的过程中获取一个枚举器[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]指向的地址的指针[ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)允许通过此过程中应用程序域的集合的迭代的实例。  
  
## <a name="remarks"></a>备注  
 应用程序域的列表基于的应用程序域中存在的快照时`EnumAppDomains`调用方法。 可能会多次调用此方法，以创建新的最新列表。 此方法的后续调用不会影响现有列表。  
  
 如果进程已终止，`EnumAppDomains`将失败，并 CORDBG_E_PROCESS_TERMINATED 的 HRESULT 值。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl、 CorPub.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorPublishProcess 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
