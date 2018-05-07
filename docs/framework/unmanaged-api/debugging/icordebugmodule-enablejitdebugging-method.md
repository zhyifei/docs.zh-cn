---
title: ICorDebugModule::EnableJITDebugging 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71722293bfb80a7e57393916560f922d970ea2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>ICorDebugModule::EnableJITDebugging 方法
控制是否在实时 (JIT) 编译器会保留为此模块中的方法的调试信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bTrackJITInfo`  
 [in]将此值设置为`true`启用 JIT 编译器，若要保留的 Microsoft 中间语言 (MSIL) 版本与此模块中的每个方法的 JIT 编译版本之间的映射信息。  
  
 `bAllowJitOpts`  
 [in]将此值设置为`true`启用 JIT 编译器生成使用用于调试的某些特定于 JIT 优化代码。  
  
## <a name="remarks"></a>备注  
 默认情况下，调试器处于活动状态时加载的所有模块的情况下，启用 JIT 调试。 以编程方式启用或禁用设置重写全局设置。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
