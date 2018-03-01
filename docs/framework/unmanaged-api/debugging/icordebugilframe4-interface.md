---
title: "ICorDebugILFrame4 接口"
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
- ICorDebugILFrame4
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1e739183-3e05-49e5-846f-4075256e41de
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66e4ba870319a1c60419ab794088a41eb9c4db3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe4-interface"></a>ICorDebugILFrame4 接口
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 提供使你能够访问中间语言 (IL) 代码的堆栈帧中的局部变量和代码的方法。 一个用于指定调试器是否可以访问在探查器 ReJIT 检测中添加的变量和代码的参数。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateLocalVariablesEx 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)|返回在当前帧中可用的局部变量的列表。|  
|[GetCodeEx 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)|返回此堆栈帧正在运行的代码。|  
|[GetLocalVariableEx 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)|返回 IL 帧中的局部变量的值。|  
  
## <a name="remarks"></a>备注  
 这些方法提供以及由提供的功能[EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)， [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)，和[GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)方法。 每个方法都包含一个 `flags` 参数，该参数可指定探查器的 ReJIT 请求定义的附加局部变量或代码是否可见。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
