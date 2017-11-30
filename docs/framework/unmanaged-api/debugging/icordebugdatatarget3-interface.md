---
title: "ICorDebugDataTarget3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1ab94e792265916e29ed24239e25cb5d57d1313
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget3-interface"></a>ICorDebugDataTarget3 接口
合理扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口以提供有关已加载模块的信息。  
  
## <a name="method"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetLoadedModules 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-getloadedmodules-method.md)|获取到目前为止已加载的模块的列表。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
