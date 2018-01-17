---
title: "ICorDebugModule3::CreateReaderForInMemorySymbols 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3.CreateReaderForInMemorySymbols
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2838c6c1fe8641e343fac1a3efa82a39ee177abc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>ICorDebugModule3::CreateReaderForInMemorySymbols 方法
创建动态模块的调试符号读取器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a>参数  
 riid  
 [in]若要返回 COM 接口的 IID。 通常，这是[ISymUnmanagedReader 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)。  
  
 ppObj  
 [out]指向返回的接口指针。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 已成功创建读取器。  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 该模块不在内存或动态模块。  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 符号尚未提供应用程序或尚不可用。  
  
 E_FAIL（或其他 E_ 返回代码）  
 无法创建读取器。  
  
## <a name="remarks"></a>备注  
 此方法还可以用于创建符号读取器对象的内存中 （非动态） 模块，但仅限于后第一次的可用符号 (由[UpdateModuleSymbols 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)回调)。  
  
 此方法返回一个新的读取器实例，每次调用 (如[CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6))。 因此，调试器应缓存结果，并且请求的新实例，仅在基础数据可能已更改时 (即，当[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)收到回调)。  
  
 动态模块没有可用的任何符号，直到已加载的第一个类型 (如所示[LoadClass 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)回调)。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 4.5、 4、 3.5 SP1  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugRemoteTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
