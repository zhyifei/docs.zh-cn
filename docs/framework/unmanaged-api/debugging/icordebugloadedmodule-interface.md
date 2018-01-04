---
title: "ICorDebugLoadedModule 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4cc7a36deb7c81ccf67427b833dead7127619b39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodule-interface"></a>ICorDebugLoadedModule 接口
提供有关已加载模块的信息。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetBaseAddress 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|获取已加载模块的基址。|  
|[GetName 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|获取加载模块的名称。|  
|[GetSize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|获取加载模块的大小（以字节为单位）。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugLoadedModule` 接口由调试器实现并且被 CLR 调试接口使用，以便从调试器中获取有关加载的模块的信息。  
  
> [!NOTE]
>  此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
