---
title: "ISymUnmanagedMethod::GetSequencePoints 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 071cbb6c33b56cb4fb409ab634a89f589db5bab8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a>ISymUnmanagedMethod::GetSequencePoints 方法
获取在此方法内的所有序列点。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a>参数  
 `cPoints`  
 [in]A`ULONG32`接收的大小`offsets`， `documents`， `lines`， `columns`， `endLines`，和`endColumns`数组。  
  
 `pcPoints`  
 [out]指向的指针`ULONG32`接收包含序列点所需的缓冲区的长度。  
  
 `offsets`  
 [in]要在其中存储 Microsoft 中间语言 (MSIL) 偏移量从开始处的序列点的方法数组。  
  
 `documents`  
 [in]在其中存储序列点所在的文档的数组。  
  
 `lines`  
 [in]在其中存储序列点所在的文档中的行的数组。  
  
 `columns`  
 [in]在其中存储序列点所在的文档中的列的数组。  
  
 `endLines`  
 [in]序列点结束的文档中的行的数组。  
  
 `endColumns`  
 [in]序列点结束的文档中的列的数组。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
