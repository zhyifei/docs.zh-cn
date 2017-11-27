---
title: "IMethodMalloc::Alloc 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc.Alloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae0fa84c08cb8e366db36b6727a3058f24789801
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc 方法
尝试为新的 Microsoft 中间语言 (MSIL) 函数主体分配指定的数量的内存。  
  
## <a name="syntax"></a>语法  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cb`  
 [in]要为方法体分配的字节数。  
  
## <a name="remarks"></a>备注  
 分配的内存将大于与此分配器相关联的模块的基址的地址处开始。 换而言之，每个分配器创建对特定模块，并且将尝试从其基址分配正偏移量的内存。 如果`Alloc`无法分配的请求大于该模块的基址的地址处的字节数它将返回 E_OUTOFMEMORY，而不考虑实际可用的内存空间量。  
  
 `Alloc`方法应与结合使用[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：** WindSee[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMethodMalloc 接口](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
