---
title: ICorDebugModule2::SetJITCompilerFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 114f4ff261d9612a81d17bf5b3df2f87323f77f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764199"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::SetJITCompilerFlags 方法
设置用于控制此 ICorDebugModule2 实时 (JIT) 编译的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `dwFlags`  
 [in]按位组合[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举值。  
  
## <a name="remarks"></a>备注  
 如果`dwFlags`值是无效的`SetJITCompilerFlags`方法将失败。  
  
 `SetJITCompilerFlags`方法可仅从调用内[icordebugmanagedcallback:: Loadmodule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)此模块的回调。 尝试调用它后`ICorDebugManagedCallback::LoadModule`回调传递将失败。  
  
 在 64 位或 Win9x 平台上不支持编辑并继续。 因此，如果您调用`SetJITCompilerFlags`CORDEBUG_JIT_ENABLE_ENC 标志设置这两个平台的任一方法`dwFlags`，则`SetJITCompilerFlags`方法和特定的所有方法编辑并继续，如[ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)，将会失败。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
