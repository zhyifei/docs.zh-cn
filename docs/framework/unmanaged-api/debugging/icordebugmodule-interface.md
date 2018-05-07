---
title: ICorDebugModule 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4a980929a644d2862a382f147505644313da7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule-interface1"></a>ICorDebugModule 接口 1
表示公共语言运行时 (CLR) 模块，这是可执行文件或动态链接库 (DLL)。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CreateBreakpoint 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|未实现。|  
|[EnableClassLoadCallbacks 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|确定是否[icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)和[icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)回调调用此模块。|  
|[EnableJITDebugging 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|确定是否在实时 (JIT) 编译器会保留为此模块中的方法的调试信息。|  
|[GetAssembly 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|获取此模块包含程序集。|  
|[GetBaseAddress 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|获取模块的基址。|  
|[GetClassFromToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|获取 ICorDebugClass 从元数据。|  
|[GetEditAndContinueSnapshot 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|已否决。|  
|[GetFunctionFromRVA 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|未实现。|  
|[GetFunctionFromToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|获取指定元数据标记的函数。|  
|[GetGlobalVariableValue 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|获取指定的全局变量的值对象。|  
|[GetMetaDataInterface 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|获取可用于检查该模块的元数据的元数据接口指针。|  
|[GetName 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|获取模块的文件名。|  
|[GetProcess 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|获取此模块包含进程。|  
|[GetSize 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|获取用字节表示的模块的大小。|  
|[GetToken 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|获取此模块的表项的令牌。|  
|[IsDynamic 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|指示是否为动态模块。|  
|[IsInMemory 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|指示仅在内存中是否存在此模块。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
