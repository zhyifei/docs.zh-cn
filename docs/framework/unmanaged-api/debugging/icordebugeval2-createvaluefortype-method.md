---
title: "ICorDebugEval2::CreateValueForType 方法"
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
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 18e7eb5fc30c27fd2c4865dc61e2f75dc9e96068
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType 方法
获取一个指向指定的类型中，新 ICorDebugValue 其初始值为零或 null。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pType`  
 [in]指向 ICorDebugType 对象表示类型的指针。  
  
 `ppValue`  
 [out]指向的地址指针`ICorDebugValue`表示的值的对象。  
  
## <a name="remarks"></a>备注  
 `CreateValueForType`通用化[icordebugeval:: Createvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md)通过允许你指定的任意对象类型，包括构造类型如`List<int>`。 此方法的唯一目的是生成一个值，可以传递给函数求值。  
  
 类型必须是一个类或值类型。 此方法不能用于创建数组值或字符串值。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
