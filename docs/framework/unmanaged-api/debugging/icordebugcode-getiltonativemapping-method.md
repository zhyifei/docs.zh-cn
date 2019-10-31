---
title: ICorDebugCode::GetILToNativeMapping 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
ms.openlocfilehash: 011da6aacbf4c40420329952f47b1fabdfc2c1a3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125631"
---
# <a name="icordebugcodegetiltonativemapping-method"></a>ICorDebugCode::GetILToNativeMapping 方法
获取 "COR_DEBUG_IL_TO_NATIVE_MAP" 实例的数组，这些实例表示从 Microsoft 中间语言（MSIL）偏移量到本机偏移量的映射。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `cMap`  
 [in] `map` 数组的大小。  
  
 `pcMap`  
 弄一个指针，指向 `map` 数组中返回的元素的实际数目。  
  
 `map`  
 弄`COR_DEBUG_IL_TO_NATIVE_MAP` 结构的数组，其中每个结构都表示从 MSIL 偏移量到本机偏移量的映射。  
  
 返回的元素数组没有排序。  
  
## <a name="remarks"></a>备注  
 仅当此 "ICorDebugCode" 实例表示实时（JIT）从 MSIL 代码编译的本机代码时，`GetILToNativeMapping` 方法才会返回有意义的结果。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugCode 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
