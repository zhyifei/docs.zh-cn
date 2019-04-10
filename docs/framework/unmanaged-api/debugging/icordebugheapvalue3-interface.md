---
title: ICorDebugHeapValue3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60d3b22d8dc140bf16af7f59781d5ed103dafbf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191700"
---
# <a name="icordebugheapvalue3-interface"></a>ICorDebugHeapValue3 接口
公开对象的监视器锁属性。 此接口扩展的 ICorDebugHeapValue 和 ICorDebugHeapValue2 接口。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetThreadOwningMonitorLock 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|返回拥有此对象的监视器锁的托管的线程。|  
|[GetMonitorEventWaitList 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|提供的监视器锁与相关联的事件的线程排队的排序的列表。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
