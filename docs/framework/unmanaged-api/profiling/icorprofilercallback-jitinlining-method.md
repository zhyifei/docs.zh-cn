---
title: "ICorProfilerCallback::JITInlining 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3990fdf1bcf76592288aac35b47b15f42cf77bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerCallback 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
