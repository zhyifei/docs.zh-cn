---
title: "SYMLINEDELTA 结构"
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
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 677b7c2858e4f3248e0d46e460b9eef09de724f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA 结构
提供有关方法的结果编辑已移动到符号处理程序信息。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`mdMethod`|方法的元数据标记。|  
|`delta`|该方法已移动的行数。|  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区结构](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
