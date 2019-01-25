---
title: AssemblyAttributesGoHereSM
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereSM
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d47ca3a9134266d1c40447cea6eb8aaf2cc9eb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706288"
---
# <a name="assemblyattributesgoheresm"></a>AssemblyAttributesGoHereSM
由 ALink 用作占位符以存储有关自定义特性的信息。  
  
## <a name="syntax"></a>语法  
  
```  
AssemblyAttributeGoHereSM  
```  
  
## <a name="remarks"></a>备注  
 对此类型的引用可能被嵌入网络模块内，模块的源包含程序集自定义属性。 当从一个或多个包含对这些类型的引用的网络模块生成程序集清单时，ALink 将使用附加到这些引用的信息来发出实际的自定义属性。 因此，此类型永远不会被实例化，而且对它的引用仅用作生成过程的一部分，在最终的程序集中不具有任何用途。  
  
 对此类型的引用指示了安全性相关的多用途自定义属性。  
  
 这些类型在 .NET Framework 中标记为“内部的”，并位于 <xref:System.Runtime.CompilerServices>。  
  
## <a name="requirements"></a>要求  
 mscorlib.dll  
  
## <a name="see-also"></a>请参阅
- [AssemblyAttributesGoHere](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)
- [AssemblyAttributesGoHereM](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereS](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)
