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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ba2b0cf7d88104eaadd434732edf3c1d4060e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422696"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags 方法
设置必须在运行时便会将该映像加载到当前过程的顺序预编译映像中嵌入的标志。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwFlags`  
 [in]值为[CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)指定的编译器标志枚举用于选择正确的预编译的映像。  
  
## <a name="remarks"></a>备注  
 `SetDesiredNGENCompilerFlags`方法指定，以便运行时将该映像加载到此过程必须预编译的映像中嵌入的标志。 此方法设置的标志仅用于选择正确的预编译的映像。 如果不存在任何此类映像，运行时将加载的 Microsoft 中间语言 (MSIL) 映像，以及在实时 (JIT) 编译器。 在这种情况下，仍必须使用调试器[icordebugmodule2:: Setjitcompilerflags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)将标志设置为 JIT 编译所需的方法。  
  
 如果图像是否加载，但某些 JIT 编译，则必须执行对该映像 （它将是这种情况，如果映像包含泛型），由指定的编译器标志`SetDesiredNGENCompilerFlags`方法将应用到额外的 JIT 编译。  
  
 `SetDesiredNGENCompilerFlags`方法必须调用期间[icordebugmanagedcallback:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)回调。 尝试调用`SetDesiredNGENCompilerFlags`方法之后将失败。 此外，将尝试设置标志，也可以定义在`CorDebugJITCompilerFlags`枚举或不合法给定进程将失败。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [ICorDebugManagedCallback 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
