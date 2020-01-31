---
title: ICorDebugAssembly 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784677"
---
# <a name="icordebugassembly-interface"></a>ICorDebugAssembly 接口

表示一个程序集。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[EnumerateModules 方法](icordebugassembly-enumeratemodules-method.md)|获取包含在程序集中的模块的枚举器。|  
|[GetAppDomain 方法](icordebugassembly-getappdomain-method.md)|获取一个接口指针，该指针指向包含此 `ICorDebugAssembly` 实例的应用程序域。|  
|[GetCodeBase 方法](icordebugassembly-getcodebase-method.md)|未在 .NET Framework 的当前版本中实现。|  
|[GetName 方法](icordebugassembly-getname-method.md)|获取程序集的名称。|  
|[GetProcess 方法](icordebugassembly-getprocess-method.md)|获取在其中运行程序集的 ICorDebugProcess 实例。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
