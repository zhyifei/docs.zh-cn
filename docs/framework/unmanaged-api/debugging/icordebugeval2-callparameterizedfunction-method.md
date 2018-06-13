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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77d9ec0cf1cbca63382e7f29de85c2f9566dc2bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416161"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>ICorDebugEval2::CallParameterizedFunction 方法
设置指定 ICorDebugFunction，可以嵌套在其构造函数采用类调用<xref:System.Type>参数或可以本身采取<xref:System.Type>参数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pFunction`  
 [in]指向的指针`ICorDebugFunction`表示被调用函数的对象。  
  
 `nTypeArgs`  
 [in]该函数采用的参数的数目。  
  
 `ppTypeArgs`  
 [in]一个指针数组，其中每个指向对象的表示的函数自变量。  
  
 `nArgs`  
 [in]在函数中传递的值的数目。  
  
 `ppArgs`  
 [in]函数参数中传递的指针，其中每个指向 ICorDebugValue 对象，表示值的数组。  
  
## <a name="remarks"></a>备注  
 `CallParameterizedFunction` 就像[icordebugeval:: Callfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md)只不过函数可能具有类型参数的类中，可能本身需要和 / 或类型参数。 对于类，然后为函数，应首先提供的类型自变量。  
  
 如果该函数是在不同的应用程序域中，则将发生转换。 但是，所有类型和值的自变量必须都是目标应用程序域中。  
  
 仅在有限情况下，可以执行函数求值。 如果`CallParameterizedFunction`或`ICorDebugEval::CallFunction`失败，返回的 HRESULT 将指示失败的最常规的可能原因。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
