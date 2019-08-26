---
title: ICorDebugILFrame2::RemapFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75004f646c01897ef3e3016b073220ad33a0d925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967583"
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction 方法
通过指定新的 Microsoft 中间语言 (MSIL) 偏移量重新映射编辑的函数  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a>参数  
 `newILOffset`  
 中堆栈帧的新 MSIL 偏移量, 应在该位置放置指令指针。 此值必须是一个序列点。  
  
 调用方负责确保此值的有效性。 例如, 如果 MSIL 偏移量在函数的边界之外, 则它是无效的。  
  
## <a name="remarks"></a>备注  
 编辑框架的函数后, 调试器可以调用`RemapFunction`方法以在框架的函数的最新版本中进行交换, 以便可以执行。 代码执行将以给定的 MSIL 偏移量开始。  
  
> [!NOTE]
> 调用`RemapFunction`(如调用[ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)) 会立即无效与为线程生成堆栈跟踪相关的所有调试接口。 这些接口包括[ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)、ICorDebugILFrame、ICorDebugInternalFrame 和 ICorDebugNativeFrame。  
  
 `RemapFunction`方法只能在当前帧的上下文中调用, 并且只能在以下情况之一中调用:  
  
- 在收到尚未继续的[ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)回调之后。  
  
- 当代码执行由于此帧的[ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)事件而停止时。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
