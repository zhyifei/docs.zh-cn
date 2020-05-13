---
title: ICorDebugFrame::CreateStepper 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 39b4e7e5123447a36254b55b6168c80e48c8dcab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205453"
---
# <a name="icordebugframecreatestepper-method"></a>ICorDebugFrame::CreateStepper 方法
获取一个分档器，该分档器允许调试器执行相对于此 ICorDebugFrame 的单步执行操作。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppStepper`  
 弄指向 ICorDebugStepper 对象地址的指针，该对象允许调试器相对于当前帧执行单步操作。  
  
## <a name="remarks"></a>备注  
 如果帧不处于活动状态，则在步骤完成之前，分档器对象通常需要返回到帧。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
