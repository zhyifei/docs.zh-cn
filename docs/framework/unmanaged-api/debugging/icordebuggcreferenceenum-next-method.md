---
title: ICorDebugGCReferenceEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: 1cf6f9c5fe8777f3333e449a804a3c3a0a64ff19
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213083"
---
# <a name="icordebuggcreferenceenumnext-method"></a>ICorDebugGCReferenceEnum::Next 方法
获取指定数量的[COR_GC_REFERENCE](cor-gc-reference-structure.md)实例，这些实例包含有关将进行垃圾回收的对象的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>参数  
 celt  
 中要检索的根的数目。  
  
 根目录  
 弄指针的数组，其中每个都指向一个[COR_GC_REFERENCE](cor-gc-reference-structure.md)对象，该对象表示要进行垃圾回收的对象的根。  
  
 pceltFetched  
 弄一个指针，指向在中实际返回的[COR_GC_REFERENCE](cor-gc-reference-structure.md)对象的数量 `roots` 。 如果 `celt` 为 1，此值可能为 `null`。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugGCReferenceEnum 接口](icordebuggcreferenceenum-interface.md)
- [调试接口](debugging-interfaces.md)
