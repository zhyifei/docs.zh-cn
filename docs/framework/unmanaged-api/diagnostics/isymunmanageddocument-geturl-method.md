---
title: "ISymUnmanagedDocument::GetURL 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetURL
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2688c2c50181c7bac7b7ee869b4e1fa5094d0ea9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgeturl-method"></a>ISymUnmanagedDocument::GetURL 方法
返回此文档的统一资源定位符 (URL)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a>参数  
 `cchUrl`  
 [in]大小，以字符为单位的`szURL`缓冲区。  
  
 `pcchUrl`  
 [out]指向接收 URL，包括 null 终止的大小的变量的指针。  
  
 `szUrl`  
 [out]包含 URL 的缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为错误代码。  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedDocument 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
