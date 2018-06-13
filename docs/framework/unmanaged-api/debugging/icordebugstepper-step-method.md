---
title: ICorDebugStepper::Step 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2d282e27ec5068fa6fe7f58ba95458fdc219972
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419219"
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step 方法
导致到单步执行其包含的线程，以及 （可选） 为此 ICorDebugStepper 继续单步执行通过该线程中调用的函数。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bStepIn`  
 [in]设置为`true`以单步执行线程中调用的函数。 设置为`false`以单步执行函数。  
  
## <a name="remarks"></a>备注  
 步骤完成时公共语言运行时执行此分档帧中的下一步的托管的指令。 如果`Step`是在分档器上调用，这不是在托管代码中，该步骤将完成时由线程执行的下一个托管的代码指令。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
