---
title: ICorDebugReferenceValue 接口
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
ms.openlocfilehash: 67006603747abd89f1b635c065860dcbe1c47a29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965635"
---
# <a name="icordebugreferencevalue-interface"></a>ICorDebugReferenceValue 接口
提供管理作为对对象的引用的值的方法。 (也就是说, 此接口提供管理指针的方法。)此接口实现 "ICorDebugValue"。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Dereference 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|获取所引用的对象。|  
|[DereferenceStrong 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|未实现。 请勿调用此方法。|  
|[GetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|获取所引用对象的当前内存地址。|  
|[IsNull 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|获取一个值, 该值指示此`ICorDebugReferenceValue`值是否为 null 值, 在这`ICorDebugReferenceValue`种情况下, 不指向对象。|  
|[SetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|设置当前内存地址。 也就是说, 此方法会将此`ICorDebugReferenceValue`设置为指向对象。|  
  
## <a name="remarks"></a>备注  
 当继续调试的进程时, 公共语言运行时 (CLR) 可能会对对象进行垃圾回收。 垃圾回收可能会在内存中移动对象。 `ICorDebugReferenceValue`将与垃圾回收一起合作, 以便在垃圾回收后更新其信息, 或者在垃圾回收之前隐式地将其无效。  
  
 继续`ICorDebugReferenceValue`调试的进程后, 对象可能会隐式失效。 派生的 "ICorDebugHandleValue" 在显式发布或公开之前不会失效。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
