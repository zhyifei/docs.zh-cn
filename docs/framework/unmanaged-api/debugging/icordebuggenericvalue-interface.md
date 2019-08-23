---
title: ICorDebugGenericValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36c2ed5529151a7ea18ccaffc2202ad6c69bcbd9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910233"
---
# <a name="icordebuggenericvalue-interface"></a>ICorDebugGenericValue 接口

"ICorDebugValue" 的子类, 适用于所有值。 此接口可为值提供 Get 和 Set 方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|将值复制到指定的缓冲区中。|  
|[SetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|从指定的缓冲区复制新值。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugGenericValue`是子接口, 因为它是不可远程处理的。  
  
 对于引用类型, 该值是引用而不是引用的内容。  
  
 此接口不支持跨计算机或跨进程远程调用。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
