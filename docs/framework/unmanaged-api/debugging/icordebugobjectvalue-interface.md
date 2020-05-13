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
ms.openlocfilehash: 603ab20b57dc4ba736b0342797d0be649a5bebc4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207479"
---
# <a name="icordebugobjectvalue-interface"></a>ICorDebugObjectValue 接口

"ICorDebugValue" 的子类，表示包含对象的值。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetClass 方法](icordebugobjectvalue-getclass-method.md)|获取一个接口指针，该指针指向此引用的对象的公共语言运行时（CLR） <xref:System.Type> `ICorDebugObjectValue` 。|  
|[GetContext 方法](icordebugobjectvalue-getcontext-method.md)|未实现。|  
|[GetFieldValue 方法](icordebugobjectvalue-getfieldvalue-method.md)|获取一个指向[ICorDebugValue](icordebugvalue-interface.md)的接口指针，该指针表示指定类的指定字段的值。|  
|[GetManagedCopy 方法](icordebugobjectvalue-getmanagedcopy-method.md)|已过时。 请勿调用此方法。|  
|[GetVirtualMethod 方法](icordebugobjectvalue-getvirtualmethod-method.md)|未实现。|  
|[IsValueClass 方法](icordebugobjectvalue-isvalueclass-method.md)|获取一个值，该值指示由此引用的对象是否 `ICorDebugObjectValue` 为值类型。|  
|[SetFromManagedCopy 方法](icordebugobjectvalue-setfrommanagedcopy-method.md)|已过时。 请勿调用此方法。|  
  
## <a name="remarks"></a>备注  
 在 `ICorDebugObjectValue` 继续进行调试之前，将一直有效。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
