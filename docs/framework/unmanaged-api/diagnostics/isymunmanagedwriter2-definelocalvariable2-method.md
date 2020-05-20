---
title: ISymUnmanagedWriter2::DefineLocalVariable2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614690"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>ISymUnmanagedWriter2::DefineLocalVariable2 方法
在当前词法范围内定义单个变量。 对于在整个范围内具有多个住宅的同名变量，可以多次调用此方法。 但在这种情况下， `startOffset` 和参数的值 `endOffset` 不能重叠。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>参数  
 `name`  
 中局部变量名称。  
  
 `attributes`  
 中局部变量特性。  
  
 `sigToken`  
 中签名的元数据标记。  
  
 `addrKind`  
 中地址类型。  
  
 `addr1`  
 中参数规范的第一个地址。  
  
 `addr2`  
 中参数规范的第二个地址。  
  
 `addr3`  
 中参数规范的第三个地址。  
  
 `startOffset`  
 中变量的起始偏移量。 该参数为可选参数。 如果为0，则忽略此参数，并在整个范围内定义变量。 如果它是非零值，则该变量将处于当前范围的偏移量内。  
  
 `endOffset`  
 中变量的结束偏移量。 该参数为可选参数。 如果为0，则忽略此参数，并在整个范围内定义变量。 如果它是非零值，则该变量将处于当前范围的偏移量内。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym .idl  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedWriter2 接口](isymunmanagedwriter2-interface.md)
- [DefineLocalVariable 方法](isymunmanagedwriter-definelocalvariable-method.md)
