---
title: "ISymUnmanagedWriter::Initialize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bae368919941e6a0b234736f789320b62405a17b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize-method"></a>ISymUnmanagedWriter::Initialize 方法
设置元数据发射器接口此编写器将与之相关联，并设置将向其写入调试符号的输出文件名称。  
  
 可以一次调用此方法，它必须在编写器的任何其他方法之前调用。 某些编写器可能需要的文件名称。 但是，始终可以向此方法，而不使用文件名的编写器任何负面影响传递文件名称。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a>参数  
 `emitter`  
 [in]指向元数据发射器接口的指针。  
  
 `filename`  
 [in]将写入调试符号的文件名。 如果为不使用文件名的编写器指定文件名，则忽略此参数。  
  
 `pIStream`  
 [in]如果指定，符号编写器将发出到符号给定<xref:System.Runtime.InteropServices.ComTypes.IStream>而不是中指定的文件`filename`参数。 `pIStream` 参数是可选的。  
  
 `fFullBuild`  
 [in]`true`如果这是完全重新生成;`false`如果这是增量编译。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>另请参阅  
 [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Initialize2 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
