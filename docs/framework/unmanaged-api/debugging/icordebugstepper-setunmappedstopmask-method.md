---
title: ICorDebugStepper::SetUnmappedStopMask 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0a273c54559e8e297e09740ba9c770ce12d72d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760581"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask 方法
设置一个值，指定在其中执行都将停止的代码未映射的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a>参数  
 `mask`  
 [in]CorDebugUnmappedStop 枚举，用于指定在其中调试程序将终止执行的代码未映射的类型的值。  
  
 默认值为 STOP_OTHER_UNMAPPED。 STOP_UNMANAGED 的值才有效，且互操作调试。  
  
## <a name="remarks"></a>备注  
 当调试器发现没有对应到 Microsoft 中间语言 (MSIL) 映射中实时 (JIT) 编译时，它暂停执行，如果已设置标志，指定该类型的非托管代码;否则，以透明方式单步执行将继续。  
  
 如果调试器不使用分档器输入一个方法，它不一定是逐未映射代码。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
