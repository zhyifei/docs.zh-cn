---
title: ICorDebugEval2::CreateValueForType 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 8632799b68ae8f92835d1774472bc1432d886f3b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793474"
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType 方法
获取一个指针，该指针指向指定类型的新 ICorDebugValue，其初始值为零或 null。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>参数  
 `pType`  
 中指向表示该类型的 ICorDebugType 对象的指针。  
  
 `ppValue`  
 弄指向表示值的 `ICorDebugValue` 对象的地址的指针。  
  
## <a name="remarks"></a>备注  
 `CreateValueForType` 通用化[ICorDebugEval：： CreateValue](icordebugeval-createvalue-method.md) ，允许指定任意对象类型，包括构造类型，如 `List<int>`。 此方法的唯一目的是生成一个可传递给函数计算的值。  
  
 类型必须是类或值类型。 不能使用此方法创建数组值或字符串值。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
