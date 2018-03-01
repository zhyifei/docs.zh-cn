---
title: "ICorProfilerCallback7::ModuleInMemorySymbolsUpdated 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 898adf043e425c00d6e311e2f67c53ed65cacb33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7::ModuleInMemorySymbolsUpdated 方法
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 每次更新与内存中模块关联的符号流时，通知探查器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleId`  
 已更新其符号流的内存中模块的标识符。  
  
## <a name="remarks"></a>备注  
 通过设置控制此回调[COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)事件掩码标志时调用[ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法。  
  
> [!NOTE]
>  将引发此事件不当前符号隐式创建或修改通过<xref:System.Reflection.Emit>Api。  
  
 甚至当符号中提供了预先的托管的重载之一调用<xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType>方法包括`rawSymbolStore`自变量指定程序集，运行时的符号可能不实际的符号的数据将与模块关联直到后[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调发生。 此事件提供了更高版本机会收集此类模块的符号。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ModuleLoadFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [SetEventMask2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [ICorProfilerCallback7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
