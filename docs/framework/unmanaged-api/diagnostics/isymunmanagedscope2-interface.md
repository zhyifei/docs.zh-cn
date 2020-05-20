---
title: ISymUnmanagedScope2 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 886ba693183a6b99eb03635e95a9661d105de40e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610855"
---
# <a name="isymunmanagedscope2-interface"></a>ISymUnmanagedScope2 接口
表示方法中的词法范围。 此接口扩展了[ISymUnmanagedScope](isymunmanagedscope-interface.md)接口，其中包含获取有关范围内定义的常量的信息的方法。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetConstantCount 方法](isymunmanagedscope2-getconstantcount-method.md)|获取在此范围中定义的常量的计数。|  
|[GetConstants 方法](isymunmanagedscope2-getconstants-method.md)|获取在此范围内定义的局部变量。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区接口](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope 接口](isymunmanagedscope-interface.md)
