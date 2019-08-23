---
title: ICorDebugObjectValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4ca59aac075a42294026ad54c5d5dd4dbf7fda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943332"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue 接口

"ICorDebugValue" 的子类, 表示包含对象的值。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md)|获取一个接口指针, 该指针指向此<xref:System.Type> `ICorDebugObjectValue`引用的对象的公共语言运行时 (CLR)。|  
|[GetContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getcontext-method.md)|未实现。|  
|[GetFieldValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getfieldvalue-method.md)|获取一个指向[ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-interface.md)的接口指针, 该指针表示指定类的指定字段的值。|  
|[GetManagedCopy 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getmanagedcopy-method.md)|已过时。 请勿调用此方法。|  
|[GetVirtualMethod 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getvirtualmethod-method.md)|未实现。|  
|[IsValueClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-isvalueclass-method.md)|获取一个值, 该值指示由此`ICorDebugObjectValue`引用的对象是否为值类型。|  
|[SetFromManagedCopy 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-setfrommanagedcopy-method.md)|已过时。 请勿调用此方法。|  
  
## <a name="remarks"></a>备注  
 在`ICorDebugObjectValue`继续进行调试之前, 将一直有效。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
