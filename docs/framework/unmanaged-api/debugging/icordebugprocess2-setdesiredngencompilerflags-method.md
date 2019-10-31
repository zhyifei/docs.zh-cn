---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 9313fc58dec8099f42dbff07685ca14791fa324f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137165"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags 方法
设置必须嵌入到预编译的映像中的标志，使运行时能够将该图像加载到当前进程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `pdwFlags`  
 中[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)枚举的一个值，该值指定用于选择正确预编译图像的编译器标志。  
  
## <a name="remarks"></a>备注  
 `SetDesiredNGENCompilerFlags` 方法指定必须嵌入到预编译的映像中的标志，以使运行时将该图像加载到此进程中。 此方法设置的标志仅用于选择正确的预编译映像。 如果不存在这样的图像，则运行时将改为加载 Microsoft 中间语言（MSIL）映像和实时（JIT）编译器。 在这种情况下，调试器仍必须使用[ICorDebugModule2：： SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)方法根据需要为 JIT 编译设置标志。  
  
 如果加载了某个映像，但对于该映像必须进行一些 JIT 编译（如果该映像包含泛型，则会出现这种情况），`SetDesiredNGENCompilerFlags` 方法指定的编译器标志将应用于额外的 JIT 编译。  
  
 在[ICorDebugManagedCallback：： CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调过程中必须调用 `SetDesiredNGENCompilerFlags` 方法。 以后尝试调用 `SetDesiredNGENCompilerFlags` 方法将失败。 另外，尝试设置未在 `CorDebugJITCompilerFlags` 枚举中定义的标志，或者对给定进程不合法的标志将失败。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
