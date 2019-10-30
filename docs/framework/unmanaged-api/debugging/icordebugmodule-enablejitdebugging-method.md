---
title: ICorDebugModule::EnableJITDebugging 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
ms.openlocfilehash: da532ee1b5909a68bedbb9e6f6c96333e88002a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109723"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a>ICorDebugModule::EnableJITDebugging 方法
控制实时（JIT）编译器是否保留此模块内的方法的调试信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a>参数  
 `bTrackJITInfo`  
 中将此值设置为 "`true`"，以使 JIT 编译器能够在此模块中的每个方法的 Microsoft 中间语言（MSIL）版本和 JIT 编译版本之间保留映射信息。  
  
 `bAllowJitOpts`  
 中将此值设置为 "`true`"，以允许 JIT 编译器生成具有特定于调试的特定于 JIT 的优化的代码。  
  
## <a name="remarks"></a>备注  
 默认情况下，调试程序处于活动状态时加载的所有模块都已启用 JIT 调试。 以编程方式启用或禁用设置将覆盖全局设置。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
