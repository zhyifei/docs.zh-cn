---
title: ICorDebugManagedCallback::UnloadClass 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadClass
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadClass method [.NET Framework debugging]
- UnloadClass method [.NET Framework debugging]
ms.assetid: 66a59b18-ce9a-41f4-b23b-4dd6753d6d36
topic_type:
- apiref
ms.openlocfilehash: a7b71170f58ddfe0295da28b8c9fc73286b074e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212264"
---
# <a name="icordebugmanagedcallbackunloadclass-method"></a>ICorDebugManagedCallback::UnloadClass 方法
通知调试器正在卸载某个类。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT UnloadClass (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugClass      *c  
);  
```  
  
## <a name="parameters"></a>参数  
 `pAppDomain`  
 中指向 ICorDebugAppDomain 对象的指针，该对象表示包含类的应用程序域。  
  
 `c`  
 中指向 ICorDebugClass 对象的指针，该对象表示类。  
  
## <a name="remarks"></a>备注  
 不应在此调用后引用此类。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [LoadClass 方法](icordebugmanagedcallback-loadclass-method.md)
- [ICorDebugManagedCallback 接口](icordebugmanagedcallback-interface.md)
