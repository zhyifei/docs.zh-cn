---
title: "ICorPublishProcess::IsManaged 方法"
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
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21fdb09820acb6357fe1457d2f96c3319b3152a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessismanaged-method"></a>ICorPublishProcess::IsManaged 方法
获取一个值，该值指示由此是否引用的进程[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)已知具有托管代码。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbManaged`  
 [out]指向一个布尔值，该值指示进程是否具有托管代码的指针。 值是`true`如果进程具有托管代码; 否则为`false`。  
  
## <a name="remarks"></a>备注  
 由于当前版本的`ICorPublishProcess`只允许访问具有托管代码中，进程`IsManaged`始终返回`true`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl、 CorPub.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorPublishProcess 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
