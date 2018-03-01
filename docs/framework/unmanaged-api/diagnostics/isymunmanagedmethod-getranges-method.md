---
title: "ISymUnmanagedMethod::GetRanges 方法"
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
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e17b411e39e522006092d79380566484f8fab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges 方法
给定文档中的一个位置，返回到的 Microsoft 中间语言 (MSIL) 的位置在此方法内包括的范围对应的开始和结束偏移量对的数组。 数组为整数的数组，其格式 [开始、 结束、 开始、 结束]。 范围对的数目是数组的除以 2 的长度。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a>参数  
 `document`  
 [in]为其请求偏移量的文档。  
  
 `line`  
 [in]与范围对应的文档行。  
  
 `column`  
 [in]与范围对应的文档列。  
  
 `cRanges`  
 [in] `ranges` 数组的大小。  
  
 `pcRanges`  
 [out]指向的指针`ULONG32`接收包含范围所需的缓冲区的大小。  
  
 `ranges`  
 [out]指向接收范围的缓冲区的指针。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
