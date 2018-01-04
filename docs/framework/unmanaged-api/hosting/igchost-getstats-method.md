---
title: "IGCHost::GetStats 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d105b0aed9c47d5e2d8ad664744e6424db63961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="igchostgetstats-method"></a>IGCHost::GetStats 方法
获取垃圾回收系统的当前状态的统计信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pStats`  
 [在中，out]指向的指针[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)包含垃圾回收系统的当前状态的统计信息的结构。  
  
## <a name="remarks"></a>备注  
 统计信息可以通过智能分配系统，用于帮助垃圾回收系统进行操作。 例如，分配系统可能会确定之后查看统计信息，它需要添加更多内存或强制进行回收。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** GCHost.idl、 GCHost.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IGCHost 接口](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
