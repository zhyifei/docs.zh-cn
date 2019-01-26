---
title: ICorDebugReferenceValue 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dbe5388d7c18202f4b89269141d33463edb07a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544268"
---
# <a name="icordebugreferencevalue-interface1"></a>ICorDebugReferenceValue 接口 1
提供管理是对对象的引用的值的方法。 （也就是说，此接口提供的指针进行管理的方法。）此接口实现"ICorDebugValue"。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Dereference 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|获取引用的对象。|  
|[DereferenceStrong 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|未实现。 请勿调用此方法。|  
|[GetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|获取被引用对象的当前内存地址。|  
|[IsNull 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|获取一个值，该值指示是否这`ICorDebugReferenceValue`这种情况下为空值，`ICorDebugReferenceValue`不指向对象。|  
|[SetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|设置当前的内存地址。 此方法，即设置此`ICorDebugReferenceValue`要指向的对象。|  
  
## <a name="remarks"></a>备注  
 调试的进程继续执行时，公共语言运行时 (CLR) 可能会执行操作对象上的垃圾回收。 垃圾回收可能会在内存中来回移动对象。 `ICorDebugReferenceValue`将协同使用垃圾回收，以便垃圾回收后, 更新其信息或将在垃圾回收之前隐式失效。  
  
 `ICorDebugReferenceValue`对象可能是隐式失效后继续调试的进程。 直到显式释放或公开，不会失效派生"ICorDebugHandleValue"。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅


- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
