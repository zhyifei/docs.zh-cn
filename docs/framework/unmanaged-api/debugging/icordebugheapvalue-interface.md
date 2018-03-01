---
title: "ICorDebugHeapValue 接口 1"
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
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2ab132b73369526204f8fd811e1567b07b4a9b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue-interface1"></a>ICorDebugHeapValue 接口 1
"ICorDebugValue"，它表示由公共语言运行时 (CLR) 垃圾回收器收集对象的子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateRelocBreakpoint 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|未实现。|  
|[IsValid 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|获取一个值，该值指示对象是否表示由此`ICorDebugHeapValue`是否有效，或者已被垃圾回收器回收。 .NET Framework 2.0 版中，此方法已被否决。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
    
    
    
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
