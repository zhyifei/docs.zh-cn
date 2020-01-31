---
title: ICorDebugThread3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 19bd869aec7e4d046890d2314f5142753ba0b112
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791393"
---
# <a name="icordebugthread3-interface"></a>ICorDebugThread3 接口
提供[ICorDebugStackWalk](icordebugstackwalk-interface.md)和相应接口的入口点。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateStackWalk 方法](icordebugthread3-createstackwalk-method.md)|为要展开其堆栈的线程创建[ICorDebugStackWalk](icordebugstackwalk-interface.md)对象。|  
|[GetActiveInternalFrames 方法](icordebugthread3-getactiveinternalframes-method.md)|返回堆栈上的内部帧（[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)对象）的数组。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugThread3` 是 ICorDebugThread 接口的逻辑扩展。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
