---
title: ICorDebugChain::GetActiveFrame 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: 03cb1556ee971124ed4c591f38d9f892fc7df7b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192145"
---
# <a name="icordebugchaingetactiveframe-method"></a>ICorDebugChain::GetActiveFrame 方法
获取链上的活动（即最近的）帧。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppFrame`  
 弄指向 ICorDebugFrame 对象的地址的指针，该对象表示链上的活动（即最近的）帧。  
  
## <a name="remarks"></a>备注  
 如果没有可用的托管堆栈帧，则 `ppFrame` 设置为 null。  
  
 如果没有可用的活动帧，则调用将成功并且 `ppFrame` 将为 null。 由于 CHAIN_ENTER_UNMANAGED 和由于 CHAIN_CLASS_INIT 而启动的某些链的原因，活动帧将不可用于启动的链。 请参阅 CorDebugChainReason 枚举。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
