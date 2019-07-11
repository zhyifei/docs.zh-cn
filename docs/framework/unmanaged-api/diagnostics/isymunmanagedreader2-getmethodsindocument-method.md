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
ms.openlocfilehash: a7fa192a8e8b8a876f672e36bb906a714b1266e2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736661"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a>ISymUnmanagedReader2::GetMethodsInDocument 方法
获取每个方法中提供的文档包含行信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a>参数  
 `document`  
 [in]指向文档的指针。  
  
 `cMethod`  
 [in]一个`ULONG32`指示的大小`pRetVal`数组。  
  
 `pcMethod`  
 [out]一个指向`ULONG32`接收包含方法所需的缓冲区的大小。  
  
 `pRetVal`  
 [out]指向接收方法的缓冲区的指针。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅

- [ISymUnmanagedReader2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
