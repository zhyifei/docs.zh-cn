---
title: "ICorDebugAssembly 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly
helpviewer_keywords: ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d08bb1d2bb7adcbdeb49cd634755d243d34d7f84
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassembly-interface1"></a>ICorDebugAssembly 接口 1
表示一个程序集。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateModules 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|获取包含在程序集中的模块的枚举数。|  
|[GetAppDomain 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|获取包含此应用程序域的接口指针`ICorDebugAssembly`实例。|  
|[GetCodeBase 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|在.NET Framework 的当前版本中未实现。|  
|[GetName 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|获取程序集的名称。|  
|[GetProcess 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|获取在其中运行该程序集的 ICorDebugProcess 实例。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
