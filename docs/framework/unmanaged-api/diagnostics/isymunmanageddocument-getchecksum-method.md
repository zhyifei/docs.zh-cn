---
title: "ISymUnmanagedDocument::GetCheckSum 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b0b2ce6facf99b44f54e8880d4436ab7fe96e50a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetchecksum-method"></a>ISymUnmanagedDocument::GetCheckSum 方法
获取校验和。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a>参数  
 `cData`  
 [in]提供的缓冲区的长度`data`参数  
  
 `pcData`  
 [out]大小和校验和，以字节为单位的长度。  
  
 `data`  
 [out]接收校验和的缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为错误代码。  
  
## <a name="see-also"></a>另请参阅  
 [ISymUnmanagedDocument 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
