---
title: ICorProfilerCallback5::ConditionalWeakTableElementReferences 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5.ConditionalWeakTableReferences
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ConditionalWeakTableElementReferences
helpviewer_keywords:
- ConditionalWeakTableElementReferences method, ICorProfilerCallback5 interface [.NET Framework profiling]
- ICorProfilerCallback5::ConditionalWeakTableElementReferences method [.NET Framework profiling]
ms.assetid: 532c7a02-a9de-4cea-bb2b-7f470da594de
topic_type:
- apiref
ms.openlocfilehash: ad721d28f6a7dc6ae0370ce10178990cb02fb9f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430049"
---
# <a name="icorprofilercallback5conditionalweaktableelementreferences-method"></a>ICorProfilerCallback5::ConditionalWeakTableElementReferences 方法

标识这些根通过直接成员字段引用和 `ConditionalWeakTable` 依赖关系引用的对象的传递闭包。

## <a name="syntax"></a>语法

```cpp
HRESULT ConditionalWeakTableElementReferences(
     [in]                     ULONG    cRootRefs,
     [in, size_is(cRootRefs)] ObjectID keyRefIds[],
     [in, size_is(cRootRefs)] ObjectID valueRefIds[],
     [in, size_is(cRootRefs)] GCHandleID rootIds[]
);
```

## <a name="parameters"></a>参数

`cRootRefs`\
[in] `keyRefIds`、`valueRefIds` 和 `rootIds` 数组中的元素数。

`keyRefIds`\
[in] 一个包含对象 ID 的数组，其中每个对象 ID 都包含相关句柄对中主要元素的 `ObjectID`。

`valueRefIds`\
[in] 一个包含对象 ID 的数组，其中每个对象 ID 都包含相关句柄对中次要元素的 `ObjectID`。 (`keyRefIds[i]` keeps `valueRefIds[i]` alive.)

`rootIds`\
[in] 一个包含 `GCHandleID` 值的数组，这些值指向包含有关垃圾回收根的附加信息的整数。

在该回调本身中，由 `ObjectID` 方法返回的任何 `ConditionalWeakTableElementReferences` 值都无效，因为垃圾回收器可能正处于将对象从旧位置移到新位置的过程中。 因此，探查器不应在 `ConditionalWeakTableElementReferences` 调用期间尝试检查对象。 在 `GarbageCollectionFinished` 时，已经将所有对象都移动到其新位置，并且检查可能已完成。

## <a name="example"></a>示例

The following code example demonstrates how to implement [ICorProfilerCallback5](icorprofilercallback5-interface.md) and use this method.

```cpp
HRESULT Callback5Impl::ConditionalWeakTableElementReferences(
    ULONG      cRootRefs,
    ObjectID   keyRefIds[],
    ObjectID   valueRefIds[],
    GCHandleID rootIds[])
{
    printf("Callback5Impl::ConditionalWeakTableElementReferences called\n");
    for (unsigned int i = 0; i < cRootRefs; ++i)
    {
        // Save dependency to XML for later retrieval
        PersistDependencyToXml(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or store dependency to an internal map
        m_cwt_deps->add_dep(rootIds[i], keyRefIds[i], valueRefIds[i]);
        // or add arc to object graph
        m_obj_graph->add_arc(keyRefIds[i], valueRefIds[i], rootIds[i]);
    }
    return S_OK;
}
```

## <a name="remarks"></a>备注

A profiler for the .NET Framework 4.5 or later versions implements the [ICorProfilerCallback5](icorprofilercallback5-interface.md) interface and records the dependencies specified by the `ConditionalWeakTableElementReferences` method. `ICorProfilerCallback5` provides the complete set of dependencies among live objects represented by `ConditionalWeakTable` entries. These dependencies and the member field references specified by the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) method enable a managed profiler to generate the full object graph of live objects.

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。

**头文件：** CorProf.idl、CorProf.h

**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

## <a name="see-also"></a>请参阅

- [ICorProfilerCallback5 接口](icorprofilercallback5-interface.md)
