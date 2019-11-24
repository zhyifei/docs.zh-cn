---
title: IMethodMalloc 接口
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 3f840154d472dbcea7dfef7ba93e38c80b836734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447550"
---
# <a name="imethodmalloc-interface"></a>IMethodMalloc 接口
Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.  
  
> [!NOTE]
> The `IMethodMalloc` interface is a simple memory allocator. It allows you to allocate memory, but not to free it.  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Alloc 方法](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|Attempts to allocate a specified amount of memory for a new MSIL function body.|  
  
## <a name="remarks"></a>备注  
 Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module. Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
