---
title: ICorDebugManagedCallback::UnloadAssembly 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 07996a78d7f559de587c8a3eb2babfc06675169d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212641"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a>ICorDebugManagedCallback::UnloadAssembly 方法
通知调试器已卸载了公共语言运行时程序集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a>参数  
 `pAppDomain`  
 中指向 ICorDebugAppDomain 对象的指针，该对象表示包含程序集的应用程序域。  
  
 `pAssembly`  
 中指向表示程序集的 ICorDebugAssembly 对象的指针。  
  
## <a name="remarks"></a>备注  
 不应在此回调后使用该程序集。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [LoadAssembly 方法](icordebugmanagedcallback-loadassembly-method.md)
- [ICorDebugManagedCallback 接口](icordebugmanagedcallback-interface.md)
