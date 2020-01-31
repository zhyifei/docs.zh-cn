---
title: ICorProfilerInfo3::GetFunctionEnter3Info 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionEnter3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionEnter3Info
helpviewer_keywords:
- GetFunctionEnter3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionEnter3Info method [.NET Framework profiling]
ms.assetid: 542c7c65-dd56-4651-b76f-5db2465e4a15
topic_type:
- apiref
ms.openlocfilehash: 55411f187e2ef73997633d94b37a7d5d2cfd74c9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868559"
---
# <a name="icorprofilerinfo3getfunctionenter3info-method"></a>ICorProfilerInfo3::GetFunctionEnter3Info 方法
提供由[FunctionEnter3WithInfo](functionenter3withinfo-function.md)函数向探查器报告的函数的堆栈帧和参数信息。 仅在 `FunctionEnter3WithInfo` 回调时可调用此方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetFunctionEnter3Info(  
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [in, out] ULONG *pcbArgumentInfo,  
            [out, size_is(*pcbArgumentInfo)]  
                  COR_PRF_FUNCTION_ARGUMENT_INFO *pArgumentInfo);  
```  
  
## <a name="parameters"></a>参数  
 `functionId`  
 [in] 正在输入的函数的 `FunctionID`。  
  
 `eltInfo`  
 [in] 表示有关给定堆栈帧的信息的不透明的句柄。 探查器应提供[FunctionEnter3WithInfo](functionenter3withinfo-function.md)函数所提供的相同 `eltInfo`。  
  
 `pFrameInfo`  
 [out] 表示有关给定堆栈帧的泛型信息的不透明的句柄。 此句柄仅在探查器调用 `GetFunctionEnter3Info` 方法的 `FunctionEnter3WithInfo` 回调时有效。  
  
 `pcbArgumentInfo`  
 [in，out]一个指针，它指向[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)结构的总大小（以字节为单位）（以及 `pArgumentInfo`所指向的参数范围的任何其他[COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md)结构）。 如果指定的大小不足，将返回 ERROR_INSUFFICIENT_BUFFER，并将预期大小存储在 `pcbArgumentInfo` 中。 若仅为检索 `*pcbArgumentInfo` 的预期值而调用 `GetFunctionEnter3Info`，请设置 `*pcbArgumentInfo`=0 和 `pArgumentInfo`=NULL。  
  
 `pArgumentInfo`  
 弄指向[COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md)结构的指针，该结构以从左到右的顺序描述函数参数在内存中的位置。  
  
## <a name="remarks"></a>备注  
 探查器必须为将进行检查的函数的 `COR_PRF_FUNCTION_ARGUMENT_INFO` 结构分配足够的空间，并且必须指示 `pcbArgumentInfo` 参数中的大小。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [ICorProfilerInfo3 接口](icorprofilerinfo3-interface.md)
- [Profiling 接口](profiling-interfaces.md)
- [分析](index.md)
