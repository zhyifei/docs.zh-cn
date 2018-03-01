---
title: "ICorDebugProcess5::EnumerateGCReferences 方法"
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
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 44975a7896c71ce8061dedde13d31c4fbb88d6a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerategcreferences-method"></a>ICorDebugProcess5::EnumerateGCReferences 方法
获取要进行垃圾回收的过程中的所有对象的枚举数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `enumerateWeakReferences`  
 [in]一个布尔值，该值指示弱引用是否也要进行枚举。 如果`enumerateWeakReferences`是`true`、`ppEnum`枚举器包括的强引用和弱引用。 如果`enumerateWeakReferences`是`false`，该枚举数包含仅的强引用。  
  
 `ppEnum`  
 [out]指向的地址的指针[ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)即的枚举数对象要进行垃圾回收。  
  
## <a name="remarks"></a>备注  
 此方法使您能够确定在进程中任何托管对象的完整根链，并且可以用于确定对象的仍处于活动状态的原因。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugProcess5 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
