---
title: ICorProfilerCallback::ObjectsAllocatedByClass 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
ms.openlocfilehash: 9ba021ec223d00e57081567b76f70f59768e6b9a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445868"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a>ICorProfilerCallback::ObjectsAllocatedByClass 方法
通知探查器自最近一次垃圾回收后已创建的每个指定类的实例数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a>参数  
 `cClassCount`  
 中`classIds` 和 `cObjects` 数组的大小。  
  
 `classIds`  
 中类 Id 的数组，其中每个 ID 指定一个包含一个或多个实例的类。  
  
 `cObjects`  
 中一个整数数组，其中每个整数指定 `classIds` 数组中相应类的实例数。  
  
## <a name="remarks"></a>备注  
 `classIds` 和 `cObjects` 数组是并行数组。 例如，`classIds[i]` 和 `cObjects[i]` 引用相同的类。 如果自上次垃圾回收后未创建类的任何实例，则忽略类。 `ObjectsAllocatedByClass` 回调不会报告在大型对象堆中分配的对象。  
  
 `ObjectsAllocatedByClass` 报告的数字仅为估算值。 对于确切计数，请使用[ICorProfilerCallback：： ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)。  
  
 如果相应的 `cObjects` 数组包含正在卸载的类型，则 `classIds` 数组可能包含一个或多个 null 项。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
