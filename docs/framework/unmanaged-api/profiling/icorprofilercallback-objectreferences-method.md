---
title: "ICorProfilerCallback::ObjectReferences 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30b8f6b5f424ff81ace36baa8d2ae39e0a2f1d1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences 方法
通知探查器在内存中由指定的对象引用的对象有关。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>参数  
 `objectId`  
 [in]引用对象的对象 ID。  
  
 `classId`  
 [in]类的指定的对象的实例 ID。  
  
 `cObjectRefs`  
 [in]由指定的对象引用的对象的数目 (即中的元素数`objectRefIds`数组)。  
  
 `objectRefIds`  
 [in]被引用的对象的 Id 的数组， `objectId`。  
  
## <a name="remarks"></a>备注  
 `ObjectReferences`针对每个垃圾回收完成后，为堆中剩余的对象调用方法。 如果探查器从此回调返回错误，则将停止分析服务下, 一次垃圾回收之前调用此回调。  
  
 `ObjectReferences`可结合使用回调[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)回调来创建运行时的完整的对象引用关系图。 公共语言运行时 (CLR) 可确保每个对象引用一次报告的`ObjectReferences`方法。  
  
 通过返回的对象 Id`ObjectReferences`不是有效在回调过程，因为垃圾回收可能正处于将对象移。 因此，探查器必须不尝试检查对象期间`ObjectReferences`调用。 当[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)调用时，垃圾回收完成集合并检查，可以安全地进行。  
  
 Null`ClassId`指示`objectId`具有正在卸载的类型。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
