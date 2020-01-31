---
title: ICorProfilerCallback::JITInlining 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 3e13b17fb03530730a78f6889309f1993419574b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866204"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining 方法
通知探查器，实时（JIT）编译器将与另一个函数插入一个函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>参数  
 `callerId`  
 中将在其中插入 `calleeId` 函数的函数的 ID。  
  
 `calleeId`  
 中要插入的函数的 ID。  
  
 `pfShouldInline`  
 [out] 用于允许插入的 `true`;否则，`false`。  
  
## <a name="remarks"></a>备注  
 探查器可以将 `pfShouldInline` 设置为 `false`，以防止 `calleeId` 函数插入 `callerId` 函数。 此外，探查器可以通过使用[COR_PRF_MONITOR](cor-prf-monitor-enumeration.md)枚举的 COR_PRF_DISABLE_INLINING 值全局禁用内联插入。  
  
 以内联方式插入的函数不会引发用于进入或离开的事件。 因此，探查器必须将 `pfShouldInline` 设置为 `false` 才能生成准确的调用图。 将 `pfShouldInline` 设置为 `false` 会影响性能，因为内联插入通常会提高速度，并减少插入方法的单独 JIT 编译事件数。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorProfilerCallback 接口](icorprofilercallback-interface.md)
