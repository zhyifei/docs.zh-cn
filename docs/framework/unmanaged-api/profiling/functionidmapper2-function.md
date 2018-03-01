---
title: "FunctionIDMapper2 函数"
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
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09aac1b9046153f56b591ac1815365ea4f90e4ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="functionidmapper2-function"></a>FunctionIDMapper2 函数
通知探查器函数的给定的标识符可能被重新映射到要在中使用的备用 ID [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)， [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)，和[FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)，或[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)， [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)，和[FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)该函数的回调。 `FunctionIDMapper2` 此外还要使探查器指示它是否想要接收该函数的回调。  
  
## <a name="syntax"></a>语法  
  
```  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a>参数  
 `funcId`  
 [in] 要重新映射的函数标识符。  
  
 `clientData`  
 [in] 指向用于消除运行时之间歧义的数据的指针。  
  
 `pbHookFunction`  
 [out] 指向一个值的指针，如果探查器想要接收 `FunctionEnter3`、`FunctionLeave3`和 `FunctionTailcall3` 或 `FunctionEnter3WithInfo`、`FunctionLeave3WithInfo` 和 `FunctionTailcall3WithInfo` 回调而将该值设置为 `true`； 否则，它会将此值设置为 `false`。  
  
## <a name="return-value"></a>返回值  
 探查器返回一个执行引擎用作替代函数标识符的值。 返回值不能为 null，除非在 `pbHookFunction` 中返回 `false`。 否则为 null 的返回值将产生不可预知的结果，包括可能停止该过程。  
  
## <a name="remarks"></a>备注  
 此方法扩展[FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)用于传递客户端数据的其他参数的函数。 客户端数据用于消除运行时之间的歧义。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Icorprofilerinfo:: Setfunctionidmapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [Icorprofilerinfo3:: Setfunctionidmapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [分析全局静态函数](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
