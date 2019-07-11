---
title: ISymUnmanagedWriter::CloseMethod 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f77f30b84622dffd8c76bb9302ad564f40ed41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778188"
---
# <a name="isymunmanagedwriterclosemethod-method"></a>ISymUnmanagedWriter::CloseMethod 方法
关闭当前方法。 一种方法关闭之后，可以在其中定义没有更多的符号。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅

- [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
