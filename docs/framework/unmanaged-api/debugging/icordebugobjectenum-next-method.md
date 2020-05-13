---
title: ICorDebugObjectEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: 70514464f27d6123a4de1d5800ed016a39541287
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207545"
---
# <a name="icordebugobjectenumnext-method"></a>ICorDebugObjectEnum::Next 方法
从当前位置开始，获取枚举中指定数量的对象的相对虚拟地址（Rva）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>参数  
 `celt`  
 [in] 要检索的对象数。  
  
 `objects`  
 弄指针的数组，其中每个都指向一个 CORDB_ADDRESS 对象。  
  
 `pceltFetched`  
 弄一个指针，指向实际返回的对象数。 如果为1，则此值可以为 null `celt` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅
