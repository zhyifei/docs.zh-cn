---
title: "ICorDebugType::GetType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c07f9974d0178a1a7502a97d54d7103ee795425f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType 方法
获取一个 CorElementType 值，描述公共语言运行时 (CLR) 的本机类型<xref:System.Type>表示通过此 ICorDebugType。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ty`  
 [out]指向的值的指针`CorElementType`枚举，指示 CLR<xref:System.Type>此`ICorDebugType`表示。  
  
## <a name="remarks"></a>备注  
 如果值`ty`ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE， [icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md)方法可调用以获取泛型类型实例化的类型; 否则，不调用`ICorDebugType::GetClass`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
