---
title: ICorDebugCode::GetCode 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: fde76c3b34fcc9f2321f3426d2801b310f681067
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179002"
---
# <a name="icordebugcodegetcode-method"></a>ICorDebugCode::GetCode 方法
获取指定函数的所有代码，这些代码为拆卸格式化。 此方法已在 .NET 框架版本 2.0 中弃用。 使用[ICorDebugCode2：：请改为获取代码块](icordebugcode2-getcodechunks-method.md)。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>parameters  
 `startOffset`  
 [在]函数开头的偏移量。  
  
 `endOffset`  
 [在]函数末尾的偏移量。  
  
 `cBufferAlloc`  
 [在]要将代码返回到`buffer`的数组的大小。  
  
 `buffer`  
 [出]将代码返回到的数组。  
  
 `pcBufferSize`  
 [出]返回的字节数。  
  
## <a name="remarks"></a>备注  
 如果函数的代码已划分为多个区块，则它们按增加本机偏移的顺序串联。 未检查指令边界。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：** 1.1， 1.0  
  
## <a name="see-also"></a>另请参阅

- [GetCodeChunks 方法](icordebugcode2-getcodechunks-method.md)
