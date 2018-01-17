---
title: "COR_PRF_FUNCTION_ARGUMENT_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e26377fe3c5cfbae68f90087e3fb624ae4db0dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentinfo-structure"></a>COR_PRF_FUNCTION_ARGUMENT_INFO 结构
按从左向右的顺序表示函数的自变量。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`numRanges`|自变量块的数量。 也就是说，此值是数[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)结构中`ranges`数组。|  
|`totalArgumentSize`|所有自变量的总大小。 换而言之，此值是自变量长度的总和。|  
|`ranges`|数组`COR_PRF_FUNCTION_ARGUMENT_RANGE`结构，其中每个表示的函数自变量的一个块。|  
  
## <a name="remarks"></a>备注  
 一个函数可能具有多个自变量。 不可能在内存中连续存储这些自变量。 你可能必须在一个位置的三个自变量的块、 在另一个位置中的两个自变量的块和最后一个块中的其他位置的一个自变量。 这些参数均为相同的函数;它们只存储在不同的位置。  
  
 `COR_PRF_FUNCTION_ARGUMENT_INFO`结构表示单个函数的所有参数。 它使用数组引用的函数自变量的所有块。 因此，对于单个函数具有单个`COR_PRF_FUNCTION_ARGUMENT_INFO`结构，即在引用多个`COR_PRF_FUNCTION_ARGUMENT_RANGE`结构，其中每个指向一个或多个函数自变量。  
  
 存储在寄存器中的自变量会溢出至内存来生成结构。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [分析结构](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
