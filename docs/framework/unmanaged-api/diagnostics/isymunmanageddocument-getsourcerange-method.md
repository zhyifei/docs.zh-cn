---
title: "ISymUnmanagedDocument::GetSourceRange 方法"
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
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dcddebbca74bb94bd2411038a02b900b2f64f2d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>ISymUnmanagedDocument::GetSourceRange 方法
返回到给定缓冲区中嵌入源的指定的范围。 缓冲区必须足够大以保存源。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a>参数  
 `startLine`  
 [in]当前文档中的起始行。  
  
 `startColumn`  
 [in]当前文档中的起始列。  
  
 `endLine`  
 [in]当前文档中的最后一行。  
  
 `endColumn`  
 [in]当前文档中最后一列。  
  
 `cSourceBytes`  
 [in]源，以字节为单位的大小。  
  
 `pcSourceBytes`  
 [out]指向接收源大小的变量的指针。  
  
 `source`  
 [out]大小和源文档，以字节为单位的指定范围的长度。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则为 S_OK。  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedDocument 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
