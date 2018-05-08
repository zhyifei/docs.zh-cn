---
title: ICorDebugCode 接口 1
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
ms.openlocfilehash: 37917577c802514fcebc3ea0792cbce9bb8a7345
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcode-interface1"></a>ICorDebugCode 接口 1
表示 Microsoft 中间语言 (MSIL) 代码段或本机代码段。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateBreakpoint 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|指定的偏移量处创建断点。|  
|[GetAddress 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|获取代码段的相对虚拟地址 (RVA)，这`ICorDebugCode`表示。|  
|[GetCode 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|获取为指定的函数，为反汇编进行格式化的所有代码。 此方法已弃用;使用[icordebugcode2:: Getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)相反。|  
|[GetEnCRemapSequencePoints 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|未实现。|  
|[GetFunction 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|获取与此关联"ICorDebugFunction" `ICorDebugCode`。|  
|[GetILToNativeMapping 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|获取表示从 MSIL 偏移量到本机偏移量的映射的"COR_DEBUG_IL_TO_NATIVE_MAP"实例的数组。|  
|[GetSize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|获取用字节表示，这表示的二进制代码的大小， `ICorDebugCode`。|  
|[GetVersionNumber 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|获取标识代码的版本的基于 1 的数字此`ICorDebugCode`表示。|  
|[IsIL 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|获取一个值，该值指示是否这`ICorDebugCode`在 MSIL 中编译。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugCode` 可以表示 MSIL 或本机代码。 表示 MSIL 代码的"ICorDebugFunction"对象可以包含零个或一个`ICorDebugCode`与它关联的对象。 一个表示本机代码的"ICorDebugFunction"对象可以具有任意数量的`ICorDebugCode`与它关联的对象。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
    
 [ICorDebugCode3 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
