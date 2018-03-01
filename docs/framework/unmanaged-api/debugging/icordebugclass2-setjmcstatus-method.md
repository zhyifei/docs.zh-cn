---
title: "ICorDebugClass2::SetJMCStatus 方法"
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
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5fa9de4482b674173dba6a8316491507330f6376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2setjmcstatus-method"></a>ICorDebugClass2::SetJMCStatus 方法
对于类的每个方法，设置一个值，该值指示方法是否是由用户定义代码。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bIsJustMyCode`  
 [in]设置为`true`以指示的方法是用户定义的代码; 否则，设置为`false`。  
  
## <a name="remarks"></a>备注  
 仅我的代码 (JMC) 分档器将跳过用户定义的代码。 用户定义的代码必须是代码的可调试的子集。  
  
 `SetJMCStatus`如果它无法设置的值的任何方法，即使它已成功设置的值对于所有其他方法，则返回 S_FALSE HRESULT 的值。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
