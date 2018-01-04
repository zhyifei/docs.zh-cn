---
title: "ICorDebugStackWalk::SetContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.SetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00e278df2b23d6fddb18c24eefb3f2aa4d1cc3cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext 方法
集[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)到有效的上下文线程对象的当前上下文。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
#### <a name="parameters"></a>参数  
 `flag`  
 [in]A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)指示上下文是来自堆栈上，活动帧，还是通过展开堆栈获取上下文的标志。  
  
 `contextSize`  
 [in]分配的大小的`CONTEXT`缓冲区。  
  
 `context`  
 [in]`CONTEXT`缓冲区。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`ICorDebugStackWalk`成功设置对象的上下文。|  
|E_FAIL|`ICorDebugStackWalk`未设置对象的上下文。|  
|E_INVALIDARG|上下文为 null。|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|太小的上下文缓冲区。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 此方法不会更改线程的当前上下文。  
  
 从堆栈查看器，将当前上下文设置为无效的上下文可能会导致不可预知的结果。  
  
 你可以通过立即调用检索此上下文的确切的按位复制[icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
