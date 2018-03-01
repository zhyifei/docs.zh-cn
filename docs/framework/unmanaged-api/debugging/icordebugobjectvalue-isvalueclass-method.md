---
title: "ICorDebugObjectValue::IsValueClass 方法"
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
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2f398de277a334a2666a12eacf6727674aed8755
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugobjectvalueisvalueclass-method"></a>ICorDebugObjectValue::IsValueClass 方法
获取一个值，该值指示此对象值是否为值类型。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbIsValueClass`  
 [out]一个布尔值，是一个指向`true`如果此"ICorDebugObjectValue"所表示的对象值是值类型，而不是引用类型; 否则为`pbIsValueClass`是`false`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
    
 
