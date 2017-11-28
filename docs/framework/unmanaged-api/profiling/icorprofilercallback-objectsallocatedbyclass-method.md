---
title: "ICorProfilerCallback::ObjectsAllocatedByClass 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectsAllocatedByClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 28c0ff537a5b2133bdeb1db8aeadf5545d8dfd0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass 方法
通知探查器有关的最新的垃圾回收后，创建的每个指定的类的实例数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a>参数  
 `cClassCount`  
 [in]大小`classIds`和`cObjects`数组。  
  
 `classIds`  
 [in]类 Id，其中每个 ID 指定的类具有一个或多个实例的数组。  
  
 `cObjects`  
 [in]一个整数，其中每个整数指定中的对应类的实例数数组`classIds`数组。  
  
## <a name="remarks"></a>备注  
 `classIds`和`cObjects`数组是并行数组。 例如，`classIds[i]`和`cObjects[i]`引用同一个类。 如果自上次垃圾回收后不创建了一个类的任何实例，则忽略该类。 `ObjectsAllocatedByClass`回调不会报告大对象堆中分配的对象。  
  
 报告的数目`ObjectsAllocatedByClass`只是估计。 精确计数，使用[icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。  
  
 `classIds`数组可能包含一个或多个 null 条目，如果相应`cObjects`数组具有要卸载的类型。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
