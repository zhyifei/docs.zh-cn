---
title: "ICorProfilerInfo3::GetFunctionLeave3Info 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 04f48562e1ddc07ad1ae166ec44ac7de8afd4312
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a>ICorProfilerInfo3::GetFunctionLeave3Info 方法
提供的堆栈帧和正在向探查器报告的函数的返回值[FunctionLeave3WithInfo 函数](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)函数。 仅在 `FunctionLeave3WithInfo` 回调时可调用此方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
#### <a name="parameters"></a>参数  
 `functionId`  
 [in]`FunctionID`返回的函数。  
  
 `eltInfo`  
 [in] 表示有关给定堆栈帧的信息的不透明的句柄。 探查器应提供相同`eltInfo`，提供给探查器[FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)函数。  
  
 `pFrameInfo`  
 [out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。 此句柄仅在探查器调用 `GetFunctionLeave3Info` 方法的 `FunctionLeave3WithInfo` 回调时有效。  
  
 `pRetvalRange`  
 [out]指向的指针[COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)结构，其中包含从函数返回的值。 若要访问返回值信息`COR_PRF_ENABLE_FUNCTION_RETVAL`必须设置标志。 探查器可以使用[icorprofilerinfo:: Seteventmask 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)设置事件标志。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [ICorProfilerInfo3 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [分析接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [分析](../../../../docs/framework/unmanaged-api/profiling/index.md)
