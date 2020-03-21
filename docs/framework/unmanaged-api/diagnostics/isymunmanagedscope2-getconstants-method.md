---
title: ISymUnmanagedScope2::GetConstants 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176612"
---
# <a name="isymunmanagedscope2getconstants-method"></a>ISymUnmanagedScope2::GetConstants 方法
获取在此作用域中定义的本地常量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a>parameters  
 `cConstants`  
 [在]`pcConstants`参数指向的缓冲区的长度。  
  
 `pcConstants`  
 [出]指向 的指针`ULONG32`，该指针以字符形式接收包含常量所需的缓冲区的大小。  
  
 `constants`  
 [出]存储常量的缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，S_OK;否则，E_FAIL或其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标题：** 科西姆.伊德尔，科西姆.h  
  
## <a name="see-also"></a>另请参阅

- [ISymUnmanagedScope2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
