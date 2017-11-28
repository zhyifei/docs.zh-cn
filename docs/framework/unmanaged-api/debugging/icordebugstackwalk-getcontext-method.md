---
title: "ICorDebugStackWalk::GetContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.GetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bdd910862e7198d616e79ec732708f708959d26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext 方法
返回在当前帧的上下文[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a>参数  
 `contextFlags`  
 [in]指示请求 （在 WinNT.h 中定义） 的上下文缓冲区的内容的标志。  
  
 `contextBufSize`  
 [in]上下文缓冲区分配的大小。  
  
 `contextSize`  
 [out]上下文的实际大小。 此值必须小于或等于的上下文缓冲区的大小。  
  
 `contextBuf`  
 [out]上下文缓冲区中。  
  
## <a name="return-value"></a>返回值  
 此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|成功地返回当前帧的上下文。|  
|E_FAIL|不会返回上下文。|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)|太小的上下文缓冲区。|  
|CORDBG_E_PAST_END_OF_STACK|帧指针是已在堆栈; 末尾因此，可以不访问任何其他帧。|  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 因为展开还原的寄存器，例如非易失寄存器的一个子集上下文在调用时可能不完全匹配的注册状态。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
