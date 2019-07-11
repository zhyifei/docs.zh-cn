---
title: ICorDebugNativeFrame2::IsMatchingParentFrame 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e215cf4f6d6c3cfde3fa723ecae67aa77e189917
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757062"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a>ICorDebugNativeFrame2::IsMatchingParentFrame 方法
确定指定的范围是否为当前帧的父级。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a>参数  
 `pPotentialParentFrame`  
 [in]指向要评估父状态的帧对象的指针。  
  
 `pIsParent`  
 [out]`true`如果`pPotentialParentFrame`作为当前帧的父级; 否则为`false`。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|成功地返回父状态。|  
|E_FAIL|不会返回父状态。|  
|E_INVALIDARG|`pPotentialParentFrame` 或 `pIsParent` 为 null。|  
  
## <a name="exceptions"></a>Exceptions  
  
## <a name="remarks"></a>备注  
 `IsMatchingParentFrame` 返回`true`框架对象传递给该方法是否在其调用该方法的帧对象的父级。 如果不是子节点指定框架的框架上调用方法，它将返回错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugNativeFrame2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
