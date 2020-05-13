---
title: ICorDebugModule::GetFunctionFromToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
ms.openlocfilehash: a33b6ff308f3444496e5a1cb2e04f28e80305db5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212573"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken 方法
获取元数据标记指定的函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>参数  
 `methodDef`  
 中`mdMethodDef`引用函数的元数据的元数据标记。  
  
 `ppFunction`  
 弄指向表示函数的 ICorDebugFunction 接口对象地址的指针。  
  
## <a name="remarks"></a>备注  
 `GetFunctionFromToken`如果传入的值 `methodDef` 不引用 Microsoft 中间语言（MSIL）方法，该方法将返回 CORDBG_E_FUNCTION_NOT_IL HRESULT。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
