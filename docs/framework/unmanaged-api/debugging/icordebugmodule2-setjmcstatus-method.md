---
title: ICorDebugModule2::SetJMCStatus 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129475"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus 方法
将此 ICorDebugModule2 中所有类的所有方法的仅我的代码（JMC）状态设置为指定的值（`pTokens` 数组中的所有方法除外），将其设置为相反值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `bIsJustMycode`  
 中如果要调试代码，则设置为 `true`;否则，设置为 `false`。  
  
 `cTokens`  
 [in] `pTokens` 数组的大小。  
  
 `pTokens`  
 中`mdToken` 值的数组，其中每个值都引用将其 JMC 状态设置为的方法！`bIsJustMycode`。  
  
## <a name="remarks"></a>备注  
 `pTokens` 数组中指定的每个方法的 JMC 状态设置为与 `bIsJustMycode` 值相反。 此模块中所有其他方法的状态将设置为 `bIsJustMycode` 值。  
  
 `SetJMCStatus` 方法将清除此模块中的所有以前的 JMC 设置。  
  
 如果已成功设置所有函数，则 `SetJMCStatus` 方法返回 S_OK HRESULT。 如果某些标记为 `true` 的函数不可调试，它将返回 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
