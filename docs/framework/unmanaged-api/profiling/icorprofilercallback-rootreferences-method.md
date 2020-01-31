---
title: ICorProfilerCallback::RootReferences 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: 948628f469eecabfbbe792dcc3edf2e1204ffc36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865956"
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences 方法
在垃圾回收后通知探查器有关根引用的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>参数  
 `cRootRefs`  
 中`rootRefIds` 数组中的引用数。  
  
 `rootRefIds`  
 中对象 Id 的数组，这些对象 Id 引用静态对象或堆栈上的对象。  
  
## <a name="remarks"></a>备注  
 同时调用 `RootReferences` 和[ICorProfilerCallback2：： RootReferences2](icorprofilercallback2-rootreferences2-method.md)来通知探查器。 探查器通常会实现一个或另一个，但不能同时实现两者，因为在 `RootReferences2` 中传递的信息是传入 `RootReferences`的超集。  
  
 `rootRefIds` 数组可以包含 null 对象。 例如，在堆栈上声明的所有对象引用都被垃圾回收器视为根，并将始终报告。  
  
 `RootReferences` 返回的对象 Id 在回调过程中无效，因为垃圾回收可能正处于将对象从旧地址移到新地址的过程中。 因此，探查器不能尝试在 `RootReferences` 调用过程中检查对象。 调用[ICorProfilerCallback2：： GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)时，所有对象已移动到它们的新位置，并且可以安全检查。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
