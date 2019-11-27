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
ms.openlocfilehash: 01404d23707be90b6b15cf741632400d49f164de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445146"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>ICorProfilerCallback::AssemblyUnloadFinished 方法
通知探查器已卸载程序集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>参数  
 `assemblyId`  
 中标识正在卸载的程序集。  
  
 `hrStatus`  
 中一个 HRESULT，指示程序集是否已成功卸载。  
  
## <a name="remarks"></a>备注  
 [ICorProfilerCallback：： AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)方法返回后，`assemblyId` 的值对信息请求无效。  
  
 在 `AssemblyUnloadFinished` 回调后，卸载程序集的某些部分可能会继续。 如果 `hrStatus` 失败，则指示失败。 不过，`hrStatus` 中的 HRESULT 成功只指示卸载程序集的第一部分已成功完成。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
