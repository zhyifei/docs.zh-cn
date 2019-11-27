---
title: ICorProfilerCallback::Initialize 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: 64df6a81eb23c20537238c702fd0c204d64d14bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434548"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize 方法
调用以在新的公共语言运行时（CLR）应用程序启动时初始化代码探查器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>参数  
 `pICorProfilerInfoUnk`  
 [在接口中](/cpp/atl/iunknown)，探查器必须查询[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)接口指针。  
  
## <a name="remarks"></a>备注  
 `Initialize` 调用是启用（或禁用）不变回叫的唯一机会。 `Initialize` 调用启用回调后，将无法在以后使用[ICorProfilerInfo：： SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)将其禁用。 [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举的 COR_PRF_MONITOR_IMMUTABLE 值指示哪些事件是不可变的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Shutdown 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
