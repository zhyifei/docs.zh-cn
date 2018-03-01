---
title: "ICorProfilerCallback4::ReJITError 方法"
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
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c746d0f7a6be96f95f1a051e22de0ad1bd2d2269
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError 方法
通知探查器在实时 (JIT) 编译器遇到重新编译过程中的错误。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>参数  
 `moduleID`  
 [in]`ModuleID`中进行重新编译失败的尝试。  
  
 `methodId`  
 [in]`MethodDef`在其上进行重新编译失败的尝试的方法。  
  
 `functionId`  
 [in]正在重新编译或已标记为重新编译函数实例。 此值可能为`NULL`如果出错而不是每个实例化安装分别为每个方法 （例如，如果探查器指定要重新编译的方法的元数据无效令牌）。  
  
 `hrStatus`  
 [in]一个 HRESULT，指示故障的性质。 请参阅值有关的列表的状态 HRESULT 部分。  
  
## <a name="return-value"></a>返回值  
 将忽略此回调的返回值。  
  
## <a name="status-hresults"></a>状态 HRESULTS  
  
|状态数组 HRESULT|描述|  
|--------------------------|-----------------|  
|E_INVALIDARG|`moduleID`或`methodDef`令牌`NULL`。|  
|CORPROF_E_DATAINCOMPLETE|该模块尚未完全加载，或正在被卸载。|  
|CORPROF_E_MODULE_IS_DYNAMIC|动态生成指定的模块 (例如，通过`Reflection.Emit`)，并因此不支持此方法。|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|方法实例化可回收程序集，并因此不能重新编译。 请注意，类型和非反射上下文中定义的函数 (例如， `List<MyCollectibleStruct>`) 可以实例化到可回收程序集。|  
|E_OUTOFMEMORY|尝试将标记为 JIT 重新编译指定的方法时，CLR 耗尽了内存。|  
|其他|操作系统返回了 CLR 控件范围之外的失败。 例如，如果要更改一个内存页的访问权限保护的系统调用失败，将显示操作系统错误。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
