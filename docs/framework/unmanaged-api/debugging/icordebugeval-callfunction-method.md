---
title: ICorDebugEval::CallFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86d48461c601b53d4461331a11a0e0ac7ddc6e7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412540"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction 方法
设置了对指定函数的调用。  
  
 此方法是.NET Framework 2.0 版中过时。 使用[icordebugeval2:: Callparameterizedfunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)相反。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pFunction`  
 [in]指向 ICorDebugFunction 对象指定要调用的函数的指针。  
  
 `nArgs`  
 [in]函数的参数的数目。  
  
 `ppArgs`  
 [in]一个指针数组，其中每个指向 ICorDebugValue 对象，它指定要传递给函数的参数。  
  
## <a name="remarks"></a>备注  
 如果该函数是虚拟的`CallFunction`将执行虚拟调度。 如果函数是在不同的应用程序域中，转换将发生，只要所有参数也都是该应用程序域中。  
  
## <a name="requirements"></a>要求  
 **平台：** WindowSee[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.1、 1.0  
  
## <a name="see-also"></a>请参阅  
 [CallParameterizedFunction 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
