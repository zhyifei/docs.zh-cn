---
title: ICorDebugNativeFrame::SetIP 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: bc33768e4155a0e272d3374d4c586c79ef2ff3fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792784"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP 方法
将指令指针设置为本机代码中的指定偏移位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>参数  
 `nOffset`  
 中本机代码中的偏移位置。  
  
## <a name="remarks"></a>备注  
 对 `SetIP` 的调用会立即使当前线程的所有帧和链无效。 如果调试器在调用 `SetIP`之后需要帧信息，则它必须执行新的堆栈跟踪。  
  
 [ICorDebug](icordebug-interface.md)将尝试保持堆栈帧处于有效状态。 但是，即使帧处于有效状态，在运行时也是如此，但仍存在一些问题，如未初始化的局部变量等。 调用方负责确保正在运行的程序的一致性。  
  
 在64位平台上，无法将指令指针移出 `catch` 或 `finally` 块。 如果调用 `SetIP` 以便在64位平台上进行此类移动，则它将返回一个指示失败的 HRESULT。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅
