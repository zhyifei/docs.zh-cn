---
title: ICorDebugStackWalk 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791882"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk 接口
提供用于获取线程堆栈上的托管方法或帧的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetContext 方法](icordebugstackwalk-getcontext-method.md)|返回 `ICorDebugStackWalk` 对象中当前帧的上下文。|  
|[SetContext 方法](icordebugstackwalk-setcontext-method.md)|将 `ICorDebugStackWalk` 对象的当前上下文设置为线程的有效上下文。|  
|[Next 方法](icordebugstackwalk-next-method.md)|将 `ICorDebugStackWalk` 对象移到下一帧。|  
|[GetFrame 方法](icordebugstackwalk-getframe-method.md)|获取 `ICorDebugStackWalk` 对象中的当前帧。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
