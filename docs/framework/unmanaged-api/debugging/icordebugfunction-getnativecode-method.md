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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0507d59011f6b584ecb1ae11c35c456c80793af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754594"
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
 [out]指向表示此函数，或者都为 null 的本机代码，如果此函数是尚未实时 (JIT) 编译的 Microsoft 中间语言 (MSIL) 代码的 ICorDebugCode 实例的指针。  
  
## <a name="remarks"></a>备注  
 如果由此函数`ICorDebugFunction`实例已 JIT 编译一次以上，对于泛型类型，如`GetNativeCode`返回随机的本机代码对象。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
