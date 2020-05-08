---
title: ICorDebugEval2::CallParameterizedFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: 72bcc2479f7b6f41b384fc2517f0b04694663398
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976143"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>ICorDebugEval2::CallParameterizedFunction 方法
设置对指定 ICorDebugFunction 的调用，此调用可以嵌套在构造函数采用<xref:System.Type>参数的类中，也可以采用<xref:System.Type>参数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `pFunction`  
 中指向`ICorDebugFunction`对象的指针，该对象表示要调用的函数。  
  
 `nTypeArgs`  
 中函数所采用的参数的数目。  
  
 `ppTypeArgs`  
 中指针的数组，其中每个都指向表示函数参数的 ICorDebugType 对象。  
  
 `nArgs`  
 中函数中传递的值的数目。  
  
 `ppArgs`  
 中指针的数组，其中每个都指向表示在函数参数中传递的值的 ICorDebugValue 对象。  
  
## <a name="remarks"></a>备注  
 `CallParameterizedFunction`类似于[ICorDebugEval：： CallFunction](icordebugeval-callfunction-method.md) ，只不过该函数可能位于具有类型参数的类中，可能本身采用类型参数或同时采用这两者。 应该首先为类提供类型参数，然后为函数指定。  
  
 如果函数在不同的应用程序域中，则会发生转换。 但是，所有类型和值参数都必须在目标应用程序域中。  
  
 仅在有限的情况下才能执行函数求值。 如果`CallParameterizedFunction`或`ICorDebugEval::CallFunction`失败，则返回的 HRESULT 将指示失败的最常见原因。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
