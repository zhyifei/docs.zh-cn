---
title: IMethodMalloc::Alloc 方法
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54c38f9a9abc9a02ba4d84c9a41b2ef6b1f7cb69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528558"
---
# <a name="imethodmallocalloc-method"></a>IMethodMalloc::Alloc 方法
尝试为新的 Microsoft 中间语言 (MSIL) 函数主体分配指定的内存量。  
  
## <a name="syntax"></a>语法  
  
```  
PVOID Alloc (  
    [in] ULONG   cb  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cb`  
 [in]要为方法主体分配的字节数。  
  
## <a name="remarks"></a>备注  
 已分配的内存将大于与此分配器相关联的模块的基址的地址处开始。 换而言之，每个分配器创建特定的模块，并将尝试从其基址分配内存的正偏移位置。 如果`Alloc`无法分配请求的数目的字节大于该模块的基址的地址处返回 E_OUTOFMEMORY，而不考虑实际的可用内存空间量。  
  
 `Alloc`方法应结合使用[icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：** WindSee[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [IMethodMalloc 接口](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)
