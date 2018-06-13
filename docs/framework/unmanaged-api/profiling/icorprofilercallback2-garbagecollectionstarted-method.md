---
title: ICorProfilerCallback2::GarbageCollectionStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a447dca98e5010163d5cc5f4f3da4333f4cdf7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455265"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted 方法
通知垃圾回收已启动代码探查器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>参数  
 `cGenerations`  
 [in]中的总项数`generationCollected`数组。  
  
 `generationCollected`  
 [in]布尔值，这些值的数组`true`如果对应的数组索引生成正在收集的此垃圾回收; 否则为`false`。  
  
 数组进行索引的值由[COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)枚举，该值指示生成。  
  
 `reason`  
 [in]值为[COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)已引发指示垃圾回收的原因的枚举。  
  
## <a name="remarks"></a>备注  
 所有适用于此垃圾回收的回调之间将发生`GarbageCollectionStarted`回调和相应[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)回调。 这些回调不需要在同一线程上发生。  
  
 它是安全的探查器检查在其原始位置中的对象`GarbageCollectionStarted`回调。 垃圾回收器将从返回后开始移动对象`GarbageCollectionStarted`。 探查器从此回调返回后，探查器应考虑为无效，直至其收到的所有对象 Id`ICorProfilerCallback2::GarbageCollectionFinished`回调。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
