---
title: ICorDebugController::Terminate 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type:
- apiref
ms.openlocfilehash: fb8cfb2d1c5902ecd0d5858ef21ba48b65b12506
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125330"
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate 方法
用指定的退出代码终止进程。  
  
> [!NOTE]
> 此方法是 Win32 `TerminateProcess` 函数的包装器。 因此，`Terminate` 以 Win32 `TerminateProcess` 函数使用的相同方式使用退出代码。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
## <a name="parameters"></a>参数  
 `exitCode`  
 中一个表示退出代码的数字值。 有效的数值是在 Winbase.h 中定义的。  
  
## <a name="remarks"></a>备注  
 如果在调用 `Terminate` 时停止该进程，则应使用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法继续此过程，以便调试器通过[ICorDebugManagedCallback：：ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)或[ICorDebugManagedCallback：： ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)回调。  
  
> [!NOTE]
> 此方法不是由应用程序域实现的。 也就是说，它不是在 <xref:System.AppDomain> 级别实现的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅
