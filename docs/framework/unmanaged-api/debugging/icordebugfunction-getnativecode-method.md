---
title: ICorDebugFunction::GetNativeCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 98aee38415709974d84873df50c39263490f2f23
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213265"
---
# <a name="icordebugfunctiongetnativecode-method"></a>ICorDebugFunction::GetNativeCode 方法
获取此 ICorDebugFunction 实例所表示的函数的本机代码。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppCode`  
 弄指向表示此函数的本机代码的 ICorDebugCode 实例的指针; 如果此函数是尚未实时（JIT）编译的 Microsoft 中间语言（MSIL）代码，则为 null。  
  
## <a name="remarks"></a>备注  
 如果此实例表示的函数已多次 `ICorDebugFunction` JIT 编译（如泛型类型），则 `GetNativeCode` 返回随机的本机代码对象。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
