---
title: "ICorDebugILFrame::SetIP 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.SetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: daffbbd9e961f4fdc7ff2e3c9be57e41e8fa3f78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframesetip-method"></a>ICorDebugILFrame::SetIP 方法
将指令指针设置为 Microsoft 中间语言 (MSIL) 代码中的指定偏移位置。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>参数  
 `nOffset`  
 中的 MSIL 代码的偏移的位置。  
  
## <a name="remarks"></a>备注  
 调用`SetIP`立即使所有帧和当前线程的链都无效。 如果调试器需要后调用的帧信息`SetIP`，则必须执行新的堆栈跟踪。  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)将尝试保留堆栈帧中的有效状态。 但是，即使的框架是处于有效状态，仍可能有问题，如未初始化的局部变量。 调用方负责确保正在运行的程序的一致性。  
  
 在 64 位平台上的指令指针不能移动外`catch`或`finally`块。 如果`SetIP`称为若要使此类移动在 64 位平台上的，它将返回 HRESULT，指示失败。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
