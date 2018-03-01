---
title: "ICorProfilerCallback5 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0406b537f6f20d7194a0115020245ade101bd498
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback5-interface"></a>ICorProfilerCallback5 接口
补充信息以帮助探查器标识活动对象的完整闭包时使用[icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)或[icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)连同方法[icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)和[ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)方法。  
  
 `ICorProfilerCallback5` 必须由托管的内存探查器实现，才能订阅与依赖句柄相关的通知。  
  
## <a name="remarks"></a>备注  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ConditionalWeakTableElementReferences 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|标识这些根通过直接成员字段引用和 `ConditionalWeakTable` 依赖关系引用的对象的传递闭包。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback2 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
