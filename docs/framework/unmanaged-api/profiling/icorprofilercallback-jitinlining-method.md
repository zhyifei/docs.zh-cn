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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 844ac2a8aad4ce2cc6f70de2d5a53c7c0b6f4f6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453139"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining 方法
通知探查器实时 (JIT) 编译器将要插入一个嵌入另一个函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a>参数  
 `callerId`  
 [in]到函数的 ID`calleeId`将插入函数。  
  
 `calleeId`  
 [in]要插入的函数 ID。  
  
 `pfShouldInline`  
 [out]`true`以允许插入发生; 否则为`false`。  
  
## <a name="remarks"></a>备注  
 探查器可以设置`pfShouldInline`到`false`以防止`calleeId`函数从要插入到`callerId`函数。 此外，探查器，可以全局禁止内联插入通过使用 COR_PRF_DISABLE_INLINING 值[COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)枚举。  
  
 内联插入函数不会引发事件进入或离开。 因此，探查器必须设置`pfShouldInline`到`false`以便生成准确的调用关系图。 设置`pfShouldInline`到`false`会影响性能，因为内联插入通常会提高速度并减少了单独的插入方法的 JIT 编译事件数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
