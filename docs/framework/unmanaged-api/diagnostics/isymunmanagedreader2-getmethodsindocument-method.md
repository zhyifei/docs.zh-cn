---
title: ISymUnmanagedReader2::GetMethodsInDocument 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 762649e260817c43291de416d2f1a92a8f03afb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427364"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a>ISymUnmanagedReader2::GetMethodsInDocument 方法
获取每个方法，提供的文档中包含行信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a>参数  
 `document`  
 [in]指向文档的指针。  
  
 `cMethod`  
 [in]A `ULONG32` ，该值指示的大小`pRetVal`数组。  
  
 `pcMethod`  
 [out]指向的指针`ULONG32`接收包含方法所需的缓冲区的大小。  
  
 `pRetVal`  
 [out]指向接收方法的缓冲区的指针。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedReader2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
