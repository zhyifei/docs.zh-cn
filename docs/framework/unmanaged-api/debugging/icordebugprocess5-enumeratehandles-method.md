---
title: "ICorDebugProcess5::EnumerateHandles 方法"
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
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c9bf9f1a4d565e0af4f3ee34a2805116407027d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumeratehandles-method"></a>ICorDebugProcess5::EnumerateHandles 方法
在进程中获取对象句柄的枚举数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a>参数  
 `types`  
 [in]按位组合[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)指定的句柄以包含在集合中的类型的值。  
  
 `ppENum`  
 [out]指向的地址的指针[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)即的枚举数对象要进行垃圾回收。  
  
## <a name="remarks"></a>备注  
 `EnumerateHandles`是一个 helper 函数，支持的句柄表的检查。 它是类似于[icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)方法，只不过而不是填充[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)集合的所有对象要进行垃圾回收，它包括具有来自句柄表的句柄的对象。  
  
 `types`参数指定要包含在集合中的句柄类型。 `types`可以是任何的以下三个成员[CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)枚举：  
  
-   `CorHandleStrongOnly`（仅引用强句柄）。  
  
-   `CorHandleWeakOnly`（仅弱引用到句柄）。  
  
-   `CorHandleAll`（所有句柄）。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
