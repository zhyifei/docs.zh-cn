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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06ce2da435df9458ca59d76fa426becbede2e619
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959679"
---
# <a name="icordebugstackwalk-interface"></a>ICorDebugStackWalk 接口
提供用于获取线程堆栈上的托管方法或帧的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|返回`ICorDebugStackWalk`对象中当前帧的上下文。|  
|[SetContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|`ICorDebugStackWalk`将对象的当前上下文设置为线程的有效上下文。|  
|[Next 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|`ICorDebugStackWalk`将对象移动到下一帧。|  
|[GetFrame 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|获取`ICorDebugStackWalk`对象中的当前帧。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
