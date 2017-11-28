---
title: "ISymUnmanagedReader::GetMethodFromDocumentPosition 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad64d5722df68859e7be9d44b94b95cf1f43823f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a>ISymUnmanagedReader::GetMethodFromDocumentPosition 方法
返回包含在文档中的给定位置处的断点的方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `document`  
 [in]指定的文档。  
  
 `line`  
 [in]指定的文档的行。  
  
 `column`  
 [in]指定的文档的列。  
  
 `pRetVal`  
 [out]指向的地址的指针[ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)表示包含该断点的方法的对象。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>另请参阅  
 [ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
