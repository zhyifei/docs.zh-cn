---
title: ICorProfilerCallback::AssemblyUnloadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6a9fe86d6160ebac084625ef94013cce9a27a3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501875"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>ICorProfilerCallback::AssemblyUnloadFinished 方法
通知探查器程序集已被卸载。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a>参数  
 `assemblyId`  
 [in]标识正在卸载的程序集。  
  
 `hrStatus`  
 [in]一个 HRESULT，指示是否已成功将程序集已被卸载。  
  
## <a name="remarks"></a>备注  
 值`assemblyId`不是有效的信息请求后[icorprofilercallback:: Assemblyunloadstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)方法返回。  
  
 卸载该程序集的某些部分可能会继续后`AssemblyUnloadFinished`回调。 失败的 HRESULT 在`hrStatus`表明发生了故障。 但是，成功的 HRESULT 在`hrStatus`仅表示已成功卸载该程序集的第一部分。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl, CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
