---
title: "ICorDebugNativeFrame2::IsChild 方法"
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
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 267bc2fcd03786bfceb218dd0218ffa7006f8fa7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2ischild-method"></a>ICorDebugNativeFrame2::IsChild 方法
确定当前帧是否子帧。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
#### <a name="parameters"></a>参数  
 `pIsChild`  
 [out]一个布尔值，指定当前帧是否子帧。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|成功地返回子状态。|  
|E_FAIL|不会返回的子状态。|  
|E_INVALIDARG|`pIsChild` 为 null。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 `IsChild`方法返回`true`框架对象在其调用方法如果是另一个帧的子级。 如果出现这种情况，使用[IsMatchingParentFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-ismatchingparentframe-method.md)方法来检查帧是否作为其父级。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugNativeFrame2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
