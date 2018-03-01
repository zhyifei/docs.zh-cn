---
title: "ISymUnmanagedMethod 接口"
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
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b6305625c3d02dbd126a284287e19b319e21eeba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod 接口
表示符号存储区内的方法。 此接口提供的一种方法，而不是与类型相关的属性仅与符号相关的属性的访问。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetNamespace 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|获取在其中定义此方法的命名空间。|  
|[GetOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|返回到文档内的给定位置在此方法的相对应的偏移量。|  
|[GetParameters 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|获取此方法的参数。|  
|[GetRanges 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|给定文档中的一个位置，返回到的 Microsoft 中间语言 (MSIL) 的位置在此方法内包括的范围对应的开始和结束偏移量对的数组。|  
|[GetRootScope 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|获取在此方法内的根词法范围。 此范围包括整个方法。|  
|[GetScopeFromOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|获取在此方法包含给定的偏移量内最封闭的词法范围。|  
|[GetSequencePointCount 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|获取在此方法内的序列点的计数。|  
|[GetSequencePoints 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|获取在此方法内的所有序列点。|  
|[GetSourceStartEnd 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|获取此方法的源的开始和结束文档位置。|  
|[GetToken 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|返回此方法的元数据标记。|  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
