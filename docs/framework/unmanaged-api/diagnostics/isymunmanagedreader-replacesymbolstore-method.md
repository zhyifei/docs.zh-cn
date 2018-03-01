---
title: "ISymUnmanagedReader::ReplaceSymbolStore 方法"
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
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bedceac4661204bb72e59981450d7fee488857b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>ISymUnmanagedReader::ReplaceSymbolStore 方法
用增量符号存储区替换现有的符号存储区。 此方法类似于是[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法，只不过给定的增量充当更新而不是完全替换。  
  
> [!NOTE]
>  你需要只能指定其中一个`filename`或`pIStream`参数，不是两个。 如果`filename`指定，则将使用该文件中的符号更新符号存储区。 如果`pIStream`存储将更新中的数据的指定<xref:System.Runtime.InteropServices.ComTypes.IStream>。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a>参数  
 `filename`  
 [in]包含符号存储区的文件的名称。  
  
 `pIStream`  
 [in]文件流，用作替代`filename`参数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
