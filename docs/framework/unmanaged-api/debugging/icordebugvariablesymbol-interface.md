---
title: ICorDebugVariableSymbol 接口
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73072dd9564853852b4d57e73c810680fdbcc4f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421332"
---
# <a name="icordebugvariablesymbol-interface"></a>ICorDebugVariableSymbol 接口
检索变量的调试符号信息。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetName 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|获取变量名。|  
|[GetSize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|获取变量的大小（以字节为单位）。|  
|[GetSlotIndex 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|获取本地变量的托管槽索引。|  
|[GetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|获取作为字节数组的变量的值。|  
|[SetValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|将字节数组的值分配给变量。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
