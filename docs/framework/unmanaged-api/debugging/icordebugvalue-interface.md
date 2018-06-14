---
title: ICorDebugValue 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fe53490014a2a7d9acc0a426613af54867599e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422118"
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue 接口 1
表示正在调试的进程中的值。 值可以是读取或写入值。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateBreakpoint 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|当前未实现此方法。|  
|[GetAddress 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|获取此地址`ICorDebugValue`对象，它是正在调试的过程中。|  
|[GetSize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|获取以字节为单位，此大小，`ICorDebugValue`对象。|  
|[GetType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|获取此的基元类型`ICorDebugValue`对象。|  
  
## <a name="remarks"></a>备注  
 一般情况下，它返回时，被传递值对象的所有权。 接收方负责完成与对象从对象中移除引用。  
  
 具体取决于其中的值从检索，值可能不会保持有效后恢复进程。 因此，一般情况下，保持的值不应在的调用[icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
    
    
    
    
 [ICorDebugValue3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
