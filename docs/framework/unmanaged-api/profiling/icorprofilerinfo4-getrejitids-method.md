---
title: ICorProfilerInfo4::GetReJITIDs 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: f6d26abba649b608858fde8beaac750600493869
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442863"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs 方法
返回 Id 的数组，这些 Id 标识仍分配的指定函数的所有 JIT 重新编译版本。 这包括 JIT 重新编译的函数版本，这些版本已进行了还原但尚未释放（例如，当包含还原函数的应用程序域仍在使用时）。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>参数  
 `functionId`  
 中要枚举其版本的函数实例的 `FunctionID`。  
  
 `cReJitIds`  
 中`reJitIds` 数组中分配的 JIT 重新编译 Id 的数目。  
  
 `pcReJitIds`  
 弄JIT 重新编译的 Id 的实际数目。  
  
 `reJitIds`  
 弄调用方分配的数组，其中包含指定函数的 JIT 重新编译的 Id。  
  
## <a name="remarks"></a>备注  
 `GetReJITIDs` 枚举给定函数实例的活动 JIT 重新编译的 Id。 它遵循的使用模式与接受调用方分配的缓冲区的其他 `ICorProfilerInfo` 函数相同。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerInfo4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [Profiling 接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
