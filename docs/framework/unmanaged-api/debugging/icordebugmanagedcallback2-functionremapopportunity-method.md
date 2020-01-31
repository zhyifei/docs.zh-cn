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
ms.openlocfilehash: bc6543b46200dd611e13bdf55aabfabd8302e70a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793338"
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
 此回调使调试器有机会通过调用[ICorDebugILFrame2：： RemapFunction](icordebugilframe2-remapfunction-method.md)方法将指令指针重新映射到指定函数的新版本中的适当位置。 如果在调用[ICorDebugController：： Continue](icordebugcontroller-continue-method.md)方法之前调试器未调用 `RemapFunction`，则运行时将继续执行旧代码，并将在下一个序列点引发另一个 `FunctionRemapOpportunity` 回调。  
  
 对于正在执行旧版本给定函数的每个帧，将调用此回调，直到调试器返回 S_OK。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugManagedCallback2 接口](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback 接口](icordebugmanagedcallback-interface.md)
