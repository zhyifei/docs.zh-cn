---
title: "ICorDebugModule2::SetJITCompilerFlags 方法"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cfc25e9ce15996360cd0e3c68805d3707b325f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::SetJITCompilerFlags 方法
设置用于控制此 ICorDebugModule2 实时 (JIT) 编译的标志。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFlags`  
 [in]按位组合[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举值。  
  
## <a name="remarks"></a>备注  
 如果`dwFlags`值无效，`SetJITCompilerFlags`方法将失败。  
  
 `SetJITCompilerFlags`方法可以调用仅从[icordebugmanagedcallback:: Loadmodule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)为此模块的回调。 尝试调用则在此之后`ICorDebugManagedCallback::LoadModule`回调传递将失败。  
  
 在 64 位或 Win9x 平台上不支持编辑并继续。 因此，如果调用`SetJITCompilerFlags`CORDEBUG_JIT_ENABLE_ENC 标志设置这两个平台中的任何一个方法`dwFlags`、`SetJITCompilerFlags`方法和特定的所有方法编辑并继续，如[ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)，将会失败。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
