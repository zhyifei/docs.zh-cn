---
title: ICorProfilerInfo::SetFunctionIDMapper 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e5d9c9596d0bb5e61bd7aed4caaa986759cfa54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455725"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a>ICorProfilerInfo::SetFunctionIDMapper 方法
指定将调用以将 `FunctionID` 值映射至替换值（传递至探查器的输入/退出挂钩）的探查器实现函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
#### <a name="parameters"></a>参数  
 `pFunc`  
 [in]指向的指针[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)实现，它将调用以映射`FunctionID`至其替换值的值。  
  
## <a name="remarks"></a>备注  
 备选方法`FunctionID`值将传递给探查器的输入/退出挂钩函数 ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)， [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)，和[FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md))指定[icorprofilerinfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)方法。  
  
 `FunctionIDMapper`只能设置一次，建议将其设置[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
