---
title: ICorDebugHeapEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: f5af8e559b4fbfeb60530372185ca10104ade987
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178848"
---
# <a name="icordebugheapenumnext-method"></a>ICorDebugHeapEnum::Next 方法
获取包含有关托管堆上对象信息的指定数量的[COR_HEAPOBJECT](cor-heapobject-structure.md)实例。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>parameters  
 celt  
 [in] 要检索的对象数。  
  
 对象  
 [出]指针数组，每个指针都[指向COR_HEAPOBJECT对象](cor-heapobject-structure.md)，该对象提供有关托管堆上的对象的信息。  
  
 pceltFetched  
 [出]指向 中实际[返回COR_HEAPOBJECT对象的](cor-heapobject-structure.md)数量的指针`objects`。 如果 `celt` 为 1，此值可能为 `null`。  
  
## <a name="remarks"></a>备注  
 `COR_HEAPOBJECT.type` 字段是嵌套的引用计数 COM 接口的标识符。 此引用必须由 `ICorDebugHeapEnum::Next` 的调用方释放。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugHeapEnum 接口](icordebugheapenum-interface.md)
- [调试接口](debugging-interfaces.md)
