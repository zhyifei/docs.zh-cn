---
title: ICorProfilerInfo10 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175065"
---
# <a name="icorprofilerinfo10-interface"></a>ICorProfilerInfo10 接口

[ICorProfilerInfo9](icorprofilerinfo9-interface.md)的子类，它提供修改函数 IL、查询运行时信息以及挂起和恢复运行时的方法。

## <a name="methods"></a>方法  

| 方法|说明|  
| ------------|-----------------|  
|[EnumerateObjectReferences 方法](icorprofilerinfo10-enumerateobjectreferences-method.md)|给定 ObjectID、回调和客户端数据，枚举每个对象引用（如果有）。 |
|[IsFrozenObject 方法](icorprofilerinfo10-isfrozenobject-method.md)|给定 ObjectID，确定对象是否位于只读段中。 |
|[GetLOHObjectSizeThreshold 方法](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|获取配置的 LOH 阈值。 |
|[RequestReJITWithInliners 方法](icorprofilerinfo10-requestrejitwithinliners-method.md)| 重新执行请求的方法，以及所请求方法的任何内衬。  |
|[SuspendRuntime 方法](icorprofilerinfo10-suspendruntime-method.md)| 在不执行 GC 的情况下挂起运行时。 |
|[ResumeRuntime 方法](icorprofilerinfo10-resumeruntime-method.md)| 在不执行 GC 的情况下恢复运行时。 |

## <a name="requirements"></a>要求  
**平台：** 请参阅[.NET Core 支持的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。  
**头文件：** CorProf.idl、CorProf.h  
**.NET 版本：**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>另请参阅

- [分析接口](profiling-interfaces.md)
