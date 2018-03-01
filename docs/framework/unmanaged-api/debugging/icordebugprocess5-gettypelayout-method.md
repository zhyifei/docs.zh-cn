---
title: "ICorDebugProcess5::GetTypeLayout 方法"
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
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4317fd374646dd5187a94f3e91cc88df939ed762
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout 方法
在根据其类型标识符的内存中获取对象的布局信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 [in]A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)指定所需其布局的类型的令牌。  
  
 `pLayout`  
 [out]指向的指针[COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)包含内存中对象的布局信息的结构。  
  
## <a name="remarks"></a>备注  
 `ICorDebugProcess5::GetTypeLayout`方法提供了有关基于对象的信息其[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)，返回由大量其他[ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)方法。 通过提供的信息[COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)通过方法来填充的结构。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [COR_TYPE_LAYOUT 结构](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 [ICorDebugProcess5 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
