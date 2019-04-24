---
title: CorDebugBlockingReason 枚举
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54652727b4684d71068a19eb5eeb2e862f413f25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215074"
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason 枚举
指定线程可能在给定对象上受到阻塞的原因。  
  
## <a name="syntax"></a>语法  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`BLOCKING_NONE`|仅限内部使用。|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|一个线程尝试获取对某个对象的监视器锁与相关联的关键部分。 通常情况下，发生这种情况时调用的一个<xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>或<xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>方法。|  
|`BLOCKING_MONITOR_EVENT`|线程正在等待的对象的监视器锁与相关联的事件。 通常情况下，发生这种情况时调用的一个<xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait`方法。|  
  
## <a name="remarks"></a>备注  
 当`BLOCKING_MONITOR_CRITICAL_SECTION`或`BLOCKING_MONITOR_EVENT`中使用成员[CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)结构，`pBlockingObject`结构指向一个表示要输入的对象的"ICorDebugValue"接口的成员. 它还保证以实现[ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
