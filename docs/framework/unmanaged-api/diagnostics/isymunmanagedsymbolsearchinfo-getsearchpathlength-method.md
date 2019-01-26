---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0672ee0e47e28afb42a533d44e83e3807b08d659
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744526"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a>ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 方法
获取搜索路径长度。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a>参数  
 `pcchPath`  
 [out]一个指向`ULONG32`用于接收大小，以字符为单位，以包含搜索路径长度的缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅
- [ISymUnmanagedSymbolSearchInfo 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
