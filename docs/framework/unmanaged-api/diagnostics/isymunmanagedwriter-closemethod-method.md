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
ms.openlocfilehash: 71be697a8a1decd9b5f780d047c3dbb397e351d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426882"
---
# <a name="isymunmanagedwriterclosemethod-method"></a>ISymUnmanagedWriter::CloseMethod 方法
关闭当前方法。 一旦关闭方法，可以在其中定义没有更多的符号。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a>返回值  
 如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [ISymUnmanagedWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
