---
title: "ICorDebugNativeFrame::SetIP 方法"
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
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 25b4f42eb6f10ecade468824d9d790a2bce740a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP 方法
将指令指针设置为指定的偏移量位置，在本机代码中。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>参数  
 `nOffset`  
 [in]本机代码中的偏移的位置。  
  
## <a name="remarks"></a>备注  
 调用`SetIP`立即使所有帧和当前线程的链都无效。 如果调试器需要后调用的帧信息`SetIP`，则必须执行新的堆栈跟踪。  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)将尝试保留堆栈帧中的有效状态。 但是，即使帧处于有效状态，就而言运行时，仍可能有问题，如未初始化的局部变量，依次类推。 调用方负责确保正在运行的程序的一致性。  
  
 在 64 位平台上的指令指针不能移动外`catch`或`finally`块。 如果`SetIP`称为若要使此类移动在 64 位平台上的，它将返回 HRESULT，指示失败。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
