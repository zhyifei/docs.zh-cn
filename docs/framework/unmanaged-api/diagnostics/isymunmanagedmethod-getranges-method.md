---
title: ISymUnmanagedMethod::GetRanges 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef5a98d510eee8942a2cad0525b6902e3e4eaa52
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769386"
---
# <a name="isymunmanagedmethodgetranges-method"></a>ISymUnmanagedMethod::GetRanges 方法
给定文档中的一个位置，返回到 Microsoft 中间语言 (MSIL) 的位置在此方法内包括的范围对应的开始和结束偏移量对的数组。 数组是一个整数数组，具有 [开始、 结束、 开始和结束] 的格式。 区域对的数目是数组除以 2 的长度。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a>参数  
 `document`  
 [in]为其请求偏移量的文档。  
  
 `line`  
 [in]与范围对应的文档行。  
  
 `column`  
 [in]与范围对应的文档列。  
  
 `cRanges`  
 [in] `ranges` 数组的大小。  
  
 `pcRanges`  
 [out]一个指向`ULONG32`接收包含多个范围所需的缓冲区的大小。  
  
 `ranges`  
 [out]指向接收范围的缓冲区的指针。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅

- [ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
