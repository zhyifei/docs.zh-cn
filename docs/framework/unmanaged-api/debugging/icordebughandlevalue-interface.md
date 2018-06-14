---
title: ICorDebugHandleValue 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6ba8a738b4086b9150e0a1c7b300a519fa3092
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419102"
---
# <a name="icordebughandlevalue-interface1"></a>ICorDebugHandleValue 接口 1
表示调试器已为其创建了垃圾回收句柄的引用值的 ICorDebugReferenceValue 子类。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Dispose 方法](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|释放此引用的句柄`ICorDebugHandleValue`而不显式释放的接口指针的对象。|  
|[GetHandleType 方法](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|获取描述的句柄引用的一个 CorDebugHandleType 值`ICorDebugHandleValue`。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugReferenceValue`对象失效的调试代码的执行中出现中断。 `ICorDebugHandleValue`显式释放前保持在中断和延续，其引用。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
