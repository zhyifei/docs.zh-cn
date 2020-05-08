---
title: ICorDebugDataTarget3 接口
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 57ef9b567d57c77c523ca6daefcf80b1d7de66d1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976403"
---
# <a name="icordebugdatatarget3-interface"></a>ICorDebugDataTarget3 接口
对[ICorDebugDataTarget](icordebugdatatarget-interface.md)接口进行逻辑扩展，以提供有关已加载模块的信息。  
  
## <a name="method"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetLoadedModules 方法](icordebugdatatarget3-getloadedmodules-method.md)|获取到目前为止已加载的模块的列表。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
