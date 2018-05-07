---
title: ICorDebugFunction2::SetJMCStatus 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15b102be5a792f982edeb320199576bdddbd859a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugfunction2setjmcstatus-method"></a>ICorDebugFunction2::SetJMCStatus 方法
将仅我的代码，表示通过此 ICorDebugFunction2 函数标记单步执行。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bIsJustMyCode`  
 [in]设置为`true`若要将函数标记为用户代码; 否则，设置为`false`。  
  
## <a name="return-values"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|`S_OK`|此函数已成功标记。|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|此函数不无法标记为用户代码，因为它不能进行调试。|  
  
## <a name="remarks"></a>备注  
 仅我的代码分档器将跳过的非用户代码。 用户代码必须是代码的可调试的子集。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
