---
title: ICorProfilerCallback2::RootReferences2 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abf92749e1139a85ea2f49fb5d5caff69ce39c24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458456"
---
# <a name="icorprofilercallback2rootreferences2-method"></a>ICorProfilerCallback2::RootReferences2 方法
垃圾回收发生后，请通知有关根引用探查器。 此方法是扩展的[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a>参数  
 `cRootRefs`  
 [in]中的元素数`rootRefIds`， `rootKinds`， `rootFlags`，和`rootIds`数组。  
  
 `rootRefIds`  
 [in]对象 Id，其中每个引用的静态对象或在堆栈上的对象的数组。 中的元素`rootKinds`数组提供信息来分类中的相应元素`rootRefIds`数组。  
  
 `rootKinds`  
 [in]数组[COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)指示垃圾回收根的类型的值。  
  
 `rootFlags`  
 [in]数组[COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)描述垃圾回收根的属性的值。  
  
 `rootIds`  
 [in]值为整数，其中包含有关垃圾回收根，具体取决于的值的其他信息的该点的 UINT_PTR 数组`rootKinds`参数。  
  
 如果类型的根是堆栈，则根 ID 将包含的变量的函数。 如果该根 ID 为 0，该函数将是一个未命名的函数，是 CLR 的内部。 如果根的类型为句柄，则根 ID 可供垃圾回收句柄。 对于其他根类型，该 ID 是不透明值，应当忽略。  
  
## <a name="remarks"></a>备注  
 `rootRefIds`， `rootKinds`， `rootFlags`，和`rootIds`数组是并行数组。 也就是说， `rootRefIds[i]`， `rootKinds[i]`， `rootFlags[i]`，和`rootIds[i]`都涉及相同的根。  
  
 同时`RootReferences`和`RootReferences2`调用以通知探查器。 探查器将通常实现一种方法或另一个，但不是同时，因为传入的信息`RootReferences2`是传入的超集`RootReferences`。  
  
 中的条目可以`rootRefIds`为零，这意味着相应的根引用为 null，并且未引用托管堆上的对象。  
  
 通过返回的对象 Id`RootReferences2`不是有效在回调过程，因为垃圾回收可能正处于将对象从旧地址移至新的地址。 因此，探查器不应在 `RootReferences2` 调用期间尝试检查对象。 当[icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)是调用，所有对象都已移到其新位置，可以安全地检查。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
