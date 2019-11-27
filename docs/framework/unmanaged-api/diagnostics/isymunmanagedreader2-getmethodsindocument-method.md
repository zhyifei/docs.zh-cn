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
ms.openlocfilehash: 70c1d87ae32fb70f8d9f6e32b527394022459526
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446434"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a>ISymUnmanagedReader2::GetMethodsInDocument 方法
获取所提供文档中包含行信息的每个方法。  
  
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
 中指向文档的指针。  
  
 `cMethod`  
 中一个 `ULONG32`，指示 `pRetVal` 数组的大小。  
  
 `pcMethod`  
 弄指向 `ULONG32` 的指针，该指针接收包含方法所需的缓冲区大小。  
  
 `pRetVal`  
 弄指向接收方法的缓冲区的指针。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedReader2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
