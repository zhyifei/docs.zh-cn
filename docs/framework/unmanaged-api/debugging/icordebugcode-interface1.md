---
title: ICorDebugCode 接口
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75cc8ea9d88dda42362f50b519864b1a78e1a64b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960795"
---
# <a name="icordebugcode-interface"></a>ICorDebugCode 接口

表示 Microsoft 中间语言 (MSIL) 代码段或本机代码段。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateBreakpoint 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|按指定的偏移量创建断点。|  
|[GetAddress 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|获取此`ICorDebugCode`表示的代码段的相对虚拟地址 (RVA)。|  
|[GetCode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|获取用于反汇编的指定函数的所有代码。 此方法已弃用;改[为使用 ICorDebugCode2:: GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 。|  
|[GetEnCRemapSequencePoints 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|未实现。|  
|[GetFunction 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|获取与此`ICorDebugCode`关联的 "ICorDebugFunction"。|  
|[GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|获取 "COR_DEBUG_IL_TO_NATIVE_MAP" 实例的数组, 这些实例表示从 MSIL 偏移量到本机偏移量的映射。|  
|[GetSize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|获取此`ICorDebugCode`表示的二进制代码的大小 (以字节为单位)。|  
|[GetVersionNumber 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|获取一个从1开始的数字, 该数字标识此`ICorDebugCode`表示的代码的版本。|  
|[IsIL 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|获取一个值, 该值指示是否`ICorDebugCode`在 MSIL 中编译此。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugCode`可以表示 MSIL 或本机代码。 表示 MSIL 代码的 "ICorDebugFunction" 对象可以有零个或一个`ICorDebugCode`关联的对象。 表示本机代码的 "ICorDebugFunction" 对象可以有任意数量的`ICorDebugCode`关联对象。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebugCode3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
