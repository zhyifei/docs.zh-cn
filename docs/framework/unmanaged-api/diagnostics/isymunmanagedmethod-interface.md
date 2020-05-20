---
title: ISymUnmanagedMethod 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615119"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod 接口
表示符号存储区中的方法。 此接口仅提供对方法的符号相关属性的访问，而不提供与类型相关的属性的访问。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetNamespace 方法](isymunmanagedmethod-getnamespace-method.md)|获取在其中定义此方法的命名空间。|  
|[GetOffset 方法](isymunmanagedmethod-getoffset-method.md)|返回此方法内的偏移量，该偏移量对应于文档中的给定位置。|  
|[GetParameters 方法](isymunmanagedmethod-getparameters-method.md)|获取此方法的参数。|  
|[GetRanges 方法](isymunmanagedmethod-getranges-method.md)|给定文档中的某个位置后，将返回与该位置涵盖在此方法中的 Microsoft 中间语言（MSIL）范围对应的起始和结束偏移量对的数组。|  
|[GetRootScope 方法](isymunmanagedmethod-getrootscope-method.md)|获取此方法内的根词法范围。 此范围包括整个方法。|  
|[GetScopeFromOffset 方法](isymunmanagedmethod-getscopefromoffset-method.md)|获取此方法内包含给定偏移量的最封闭的词法范围。|  
|[GetSequencePointCount 方法](isymunmanagedmethod-getsequencepointcount-method.md)|获取此方法中序列点的计数。|  
|[GetSequencePoints 方法](isymunmanagedmethod-getsequencepoints-method.md)|获取此方法中的所有序列点。|  
|[GetSourceStartEnd 方法](isymunmanagedmethod-getsourcestartend-method.md)|获取此方法的源的起始和结束文档位置。|  
|[GetToken 方法](isymunmanagedmethod-gettoken-method.md)|返回此方法的元数据标记。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区接口](diagnostics-symbol-store-interfaces.md)
