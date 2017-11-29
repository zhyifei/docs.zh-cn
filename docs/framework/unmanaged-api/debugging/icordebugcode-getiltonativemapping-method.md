---
title: "ICorDebugCode::GetILToNativeMapping 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetILToNativeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54937e8d5d7a2e345ebcbccadbc592b12e3ee9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetiltonativemapping-method"></a>ICorDebugCode::GetILToNativeMapping 方法
获取表示 microsoft 中间语言 (MSIL) 偏移量到本机偏移量的映射的"COR_DEBUG_IL_TO_NATIVE_MAP"实例的数组。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cMap`  
 [in] `map` 数组的大小。  
  
 `pcMap`  
 [out]指向元素中返回的实际数目`map`数组。  
  
 `map`  
 [out]数组`COR_DEBUG_IL_TO_NATIVE_MAP`结构，其中每个表示从 MSIL 偏移量到本机偏移量的映射。  
  
 没有任何返回的元素数组的排序。  
  
## <a name="remarks"></a>备注  
 `GetILToNativeMapping`方法返回有意义的结果，仅当此"icor 调试代码"实例表示了实时 (JIT) 编译的 MSIL 代码中的本机代码。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorDebugCode 接口 1](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
