---
title: ICorDebugBreakpoint Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a222f578daed0ab81e2136e00d6f9b032acd95fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744929"
---
# <a name="icordebugbreakpoint-interface1"></a>ICorDebugBreakpoint Interface1
表示一个函数或对值的观察点中的断点。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Activate 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|设置此活动的状态`ICorDebugBreakpoint`。|  
|[IsActive 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|获取一个值，该值指示是否此`ICorDebugBreakpoint`处于活动状态。|  
  
## <a name="remarks"></a>备注  
 断点不直接支持条件表达式。 如果需要此类功能，则调试程序必须实现它的`ICorDebugBreakpoint`。  
  
 ICorDebugFunctionBreakpoint 接口扩展`ICorDebugBreakpoint`以支持函数中的断点。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
