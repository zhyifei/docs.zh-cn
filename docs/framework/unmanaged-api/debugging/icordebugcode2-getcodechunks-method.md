---
title: ICorDebugCode2::GetCodeChunks 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bdaf6391ca5c19f073708d6258ad5775bec9824
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700727"
---
# <a name="icordebugcode2getcodechunks-method"></a>ICorDebugCode2::GetCodeChunks 方法

获取包含此代码对象的代码块。

## <a name="syntax"></a>语法

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a>Parameters

 `cbufSize`  
 中@No__t-0 数组的大小。

 `pcnumChunks`  
 弄@No__t-0 数组中返回的块区数。

 `chunks`  
 弄"CodeChunkInfo" 结构的数组，其中每个结构都表示一个代码块。 如果 @no__t 的值为0，则此参数可以为 null。

## <a name="remarks"></a>备注

 代码块将永远不会重叠，它们将遵循[ICorDebugCode：： GetCode](icordebugcode-getcode-method.md)连接的顺序。 .NET Framework 版本2.0 中的 Microsoft 中间语言（MSIL）代码对象将包含一个代码块。

## <a name="requirements"></a>要求

 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。

 **标头：** Cordebug.idl，Cordebug.idl

 **类库**CorGuids.lib

 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
 
