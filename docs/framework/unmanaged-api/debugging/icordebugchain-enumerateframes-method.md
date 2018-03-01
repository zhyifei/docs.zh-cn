---
title: "ICorDebugChain::EnumerateFrames 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d9df99c239568948c04f61ca4ec5e2b9207930f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames 方法
获取一个枚举器包含的链中的所有托管的堆栈帧并从最新帧开始。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppFrames`  
 [out]指向一个 ICorDebugFrameEnum 对象，它的堆栈帧的枚举器的地址的指针。  
  
## <a name="remarks"></a>备注  
 链表示线程的物理调用堆栈。  
  
 `EnumerateFrames`应该仅用于托管链的调用方法。 调试 API 不提供用于获取非托管链中包含的帧的方法。 调试器必须使用其他方法来获取此信息。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
