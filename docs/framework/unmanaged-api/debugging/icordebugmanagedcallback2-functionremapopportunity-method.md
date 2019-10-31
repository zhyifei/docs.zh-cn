---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: c6c361113a441df050a8e7cd5219819cc8332581
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131480"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a>ICorDebugManagedCallback2::FunctionRemapOpportunity 方法
通知调试程序代码执行已到达已编辑函数的较早版本中的序列点。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a>参数  
 `pAppDomain`  
 中指向 ICorDebugAppDomain 对象的指针，该对象表示包含已编辑函数的应用程序域。  
  
 `pThread`  
 中指向 ICorDebugThread 对象的指针，该对象表示遇到重新映射断点的线程。  
  
 `pOldFunction`  
 中指向 ICorDebugFunction 对象的指针，该对象表示线程上当前正在运行的函数的版本。  
  
 `pNewFunction`  
 中指向 ICorDebugFunction 对象的指针，该对象表示函数的最新版本。  
  
 `oldILOffset`  
 中函数的旧版本中指令指针的 Microsoft 中间语言（MSIL）偏移量。  
  
## <a name="remarks"></a>备注  
 此回调使调试器有机会通过调用[ICorDebugILFrame2：： RemapFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)方法将指令指针重新映射到指定函数的新版本中的适当位置。 如果在调用[ICorDebugController：： Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)方法之前调试器未调用 `RemapFunction`，则运行时将继续执行旧代码，并将在下一个序列点引发另一个 `FunctionRemapOpportunity` 回调。  
  
 对于执行较早版本给定函数的每个帧，将调用此回调，直到调试器返回 S_OK。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugManagedCallback2 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
