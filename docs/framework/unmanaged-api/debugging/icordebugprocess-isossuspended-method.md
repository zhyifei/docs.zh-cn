---
title: ICorDebugProcess::IsOSSuspended 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: 21da69d4bff0f17eb607dda45fb7dbafea8c59f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128772"
---
# <a name="icordebugprocessisossuspended-method"></a>ICorDebugProcess::IsOSSuspended 方法
获取一个值，该值指示是否由于调试器停止此进程而挂起了指定线程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>参数  
 `threadID`  
 中相关线程的 ID。  
  
 `pbSuspended`  
 弄一个指向布尔值的指针，如果指定线程已挂起，则该指针 `true`;否则为 `false``pbSuspended`。  
  
## <a name="remarks"></a>备注  
 当由于调试器停止此进程而暂停指定的线程时，指定线程的 Win32 挂起计数将递增1。 如果调试器用户界面（UI）向用户显示线程的操作系统（OS）挂起计数，则可能需要考虑此信息。  
  
 `IsOSSuspended` 方法仅在非托管调试的上下文中有意义。 在托管调试期间，线程会以协作方式暂停，而不是由 OS 挂起。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
