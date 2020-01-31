---
title: ICorProfilerCallback::AssemblyLoadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: 15ce195af0c0e8f8777f6e5d02043e17e32308da
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866638"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>ICorProfilerCallback::AssemblyLoadFinished 方法
通知探查器程序集已完成加载。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>参数

- `assemblyId`

  \[中的] 标识已加载的程序集。

- `hrStatus`

  \[中的] HRESULT，指示程序集是否已成功加载。

## <a name="remarks"></a>备注  
 在调用 `AssemblyLoadFinished` 方法之前，`assemblyId` 的值对信息请求无效。  
  
 在 `AssemblyLoadFinished` 回调后，加载程序集的某些部分可能会继续。 如果 `hrStatus` 失败，则指示失败。 不过，`hrStatus` 中的 HRESULT 成功只指示加载程序集的第一部分已成功完成。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
