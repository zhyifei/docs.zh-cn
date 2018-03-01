---
title: "ISymUnmanagedScope 接口"
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
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e4d4c83b754945c126913a9d96db47966959fed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope 接口
表示的方法内的词法范围。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetChildren 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|获取此作用域的子级。|  
|[GetEndOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|获取此范围的结束偏移量。|  
|[GetLocalCount 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|获取此范围内定义的本地变量的计数。|  
|[GetLocals 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|获取此范围内定义的本地变量。|  
|[GetMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|获取包含此作用域的方法。|  
|[GetNamespaces 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|获取在此作用域中使用的命名空间。|  
|[GetParent 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|获取此作用域的父作用域。|  
|[GetStartOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|获取此范围的起始偏移量。|  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedScope2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
