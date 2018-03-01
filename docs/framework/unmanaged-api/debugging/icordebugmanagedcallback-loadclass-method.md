---
title: "ICorDebugManagedCallback::LoadClass 方法"
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
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f3e732b418398e9c917085d22507c9304981b06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>ICorDebugManagedCallback::LoadClass 方法
通知调试器已加载的类。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAppDomain`  
 [in]指向一个表示已向其中加载类的应用程序域的 ICorDebugAppDomain 对象的指针。  
  
 `c`  
 [in]指向一个 ICorDebugClass 对象，表示类的指针。  
  
## <a name="remarks"></a>备注  
 仅当包含的类模块启用了类加载，则会发生此回调。 类加载的动态模块始终处于启用状态。  
  
 `LoadClass`回调提供适当的时候将断点绑定到动态模块中的新生成类。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [UnloadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
