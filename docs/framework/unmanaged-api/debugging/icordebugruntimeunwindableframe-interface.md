---
title: "ICorDebugRuntimeUnwindableFrame 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnwindableFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnwindableFrame
helpviewer_keywords: ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80b4212691784d88c92235a5c5c65acaee165201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a>ICorDebugRuntimeUnwindableFrame 接口
提供对非托管方法的支持，这些方法需要公共语言运行时 (CLR) 来展开帧。  
  
## <a name="remarks"></a>备注  
 `ICorDebugRuntimeUnwindableFrame`ICorDebugFrame 接口的专用的版本。 它使用非托管需要运行时，若要展开当前堆栈上的某个帧的方法。 现有的展开约定无效，因为它们不使用 JIT 编译的代码。 当调试器发现不可展开的框架时，它应使用[icordebugstackwalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)方法来展开它，但它应执行检查本身。 当调试器收到`ICorDebugRuntimeUnwindableFrame`，它可以调用[icordebugstackwalk:: Getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)方法来检索帧的上下文。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
