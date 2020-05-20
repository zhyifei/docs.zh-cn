---
title: ISymUnmanagedScope 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615340"
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope 接口
表示方法中的词法范围。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetChildren 方法](isymunmanagedscope-getchildren-method.md)|获取此作用域的子级。|  
|[GetEndOffset 方法](isymunmanagedscope-getendoffset-method.md)|获取此范围的结束偏移量。|  
|[GetLocalCount 方法](isymunmanagedscope-getlocalcount-method.md)|获取在此范围内定义的局部变量的计数。|  
|[GetLocals 方法](isymunmanagedscope-getlocals-method.md)|获取在此范围内定义的局部变量。|  
|[GetMethod 方法](isymunmanagedscope-getmethod-method.md)|获取包含此范围的方法。|  
|[GetNamespaces 方法](isymunmanagedscope-getnamespaces-method.md)|获取正在此范围内使用的命名空间。|  
|[GetParent 方法](isymunmanagedscope-getparent-method.md)|获取此范围的父范围。|  
|[GetStartOffset 方法](isymunmanagedscope-getstartoffset-method.md)|获取此范围的起始偏移量。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区接口](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2 接口](isymunmanagedscope2-interface.md)
