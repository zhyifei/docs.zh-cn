---
title: "ICorDebugModule2::SetJMCStatus 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a461a9c05b18de45426247743c6e4ffca775025a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2setjmcstatus-method"></a>ICorDebugModule2::SetJMCStatus 方法
设置的所有类的所有方法的仅我的代码 (JMC) 状态中到指定的值，除中此 ICorDebugModule2`pTokens`数组，它将设置为的相反值。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bIsJustMycode`  
 [in]设置为`true`代码是调试; 否则为如果设置为`false`。  
  
 `cTokens`  
 [in] `pTokens` 数组的大小。  
  
 `pTokens`  
 [in]数组`mdToken`值，其中每个是指将具有设置为其 jmc 的方法状态的方法 ！`bIsJustMycode`。  
  
## <a name="remarks"></a>备注  
 中指定每个方法的 JMC 状态`pTokens`数组设置为相反`bIsJustMycode`值。 此模块中的所有其他方法的状态设置为`bIsJustMycode`值。  
  
 `SetJMCStatus`方法清除在此模块中的所有先前 jmc 的方法设置。  
  
 `SetJMCStatus`方法返回，则为 S_OK HRESULT，如果所有函数已成功都设置。 它将返回标记一些函数，如果 CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT`true`不是可调试。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
