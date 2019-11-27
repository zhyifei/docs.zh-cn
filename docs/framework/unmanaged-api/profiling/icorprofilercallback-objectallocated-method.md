---
title: ICorProfilerCallback::ObjectAllocated 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 66643bbb8dbc914b2e0e48a7f0c87630fe95e5d3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445853"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>ICorProfilerCallback::ObjectAllocated 方法
通知探查器已为对象分配堆中的内存。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>参数  
 `objectId`  
 中为其分配内存的对象的 ID。  
  
 `classId`  
 中对象为其实例的类的 ID。  
  
## <a name="remarks"></a>备注  
 不会为堆栈或非托管内存中的分配调用 `ObjectedAllocated` 方法。 `classId` 参数可以引用尚未加载的托管代码中的类。 探查器将在 `ObjectAllocated` 回调后立即收到该类的类加载回调。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ClassLoadStarted 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [ClassLoadFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
