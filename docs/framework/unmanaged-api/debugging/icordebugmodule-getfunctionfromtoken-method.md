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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 547986633172d6f5e6549ad2048833dc9fb0cef3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763464"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>ICorDebugModule::GetFunctionFromToken 方法
获取指定的元数据标记的函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>参数  
 `methodDef`  
 [in]一个`mdMethodDef`元数据标记所引用的函数的元数据。  
  
 `ppFunction`  
 [out]ICorDebugFunction 接口对象，表示该函数的地址指针。  
  
## <a name="remarks"></a>备注  
 `GetFunctionFromToken`如果中传递的值，方法将返回 CORDBG_E_FUNCTION_NOT_IL HRESULT`methodDef`不引用 Microsoft 中间语言 (MSIL) 方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
