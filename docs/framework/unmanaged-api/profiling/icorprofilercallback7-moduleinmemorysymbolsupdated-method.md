---
title: ICorProfilerCallback7：： ModuleInMemorySymbolsUpdated 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: f6dd10d196ffd3a653584e1bc8d1a5643850bc33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136608"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7：： ModuleInMemorySymbolsUpdated 方法
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 只要更新与内存中模块关联的符号流，就会通知探查器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>参数  
 [in] `moduleId`  
 已更新其符号流的内存中模块的标识符。  
  
## <a name="remarks"></a>备注  
 调用[ICorProfilerCallback5：： SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)方法时，可通过设置[COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)事件掩码标志来控制此回调。  
  
> [!NOTE]
> 当前不会对通过 <xref:System.Reflection.Emit> Api 隐式创建或修改的符号引发此事件。  
  
 即使在对托管 <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> 方法的重载之一的调用中提供了符号（包括 `rawSymbolStore` 参数以指定程序集的符号），运行时也不会实际将符号数据与模块相关联，直到发生了[ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)回调。 此事件提供稍后的机会来收集此类模块的符号。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ModuleLoadFinished 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [ICorProfilerCallback7 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
