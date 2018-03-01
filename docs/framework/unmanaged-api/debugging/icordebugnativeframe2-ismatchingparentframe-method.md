---
title: "ICorDebugNativeFrame2::IsMatchingParentFrame 方法"
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
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc2d8eacb05e861290ad19a34c261943dc2959a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a>ICorDebugNativeFrame2::IsMatchingParentFrame 方法
确定是否为指定的框架为当前帧的父级。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a>参数  
 `pPotentialParentFrame`  
 [in]指向想要评估父状态框架对象的指针。  
  
 `pIsParent`  
 [out]`true`如果`pPotentialParentFrame`是当前帧的父级; 否则为`false`。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|成功地返回父状态。|  
|E_FAIL|不会返回父状态。|  
|E_INVALIDARG|`pPotentialParentFrame` 或 `pIsParent` 为 null。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 `IsMatchingParentFrame`返回`true`框架对象传递给该方法是否在其调用方法帧对象的父级。 如果你在不是为指定框架的子级的帧上调用方法时，它将返回错误。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugNativeFrame2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
