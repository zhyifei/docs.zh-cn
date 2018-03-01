---
title: "“Cor调试状态已更改”枚举"
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
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: da9d2bb793340aa4736e0b26ab9bf9d5ec7c546a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugstatechange-enumeration"></a>“Cor调试状态已更改”枚举
描述基于进程变化必须删除的缓存数据数量。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`PROCESS_RUNNING`|该进程向前执行，达到了一种新的内存状态。|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|进程的内存可能与以往截然不同。|  
  
## <a name="remarks"></a>备注  
 成员`CorDebugStateChange`当调试器调用时，作为参数提供的枚举[进程状态已更改](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)方法  
  
> [!NOTE]
>  此枚举仅用于 .NET Native 调试方案。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试枚举](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
