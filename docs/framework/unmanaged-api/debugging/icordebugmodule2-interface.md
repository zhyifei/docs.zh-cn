---
title: ICorDebugModule2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 7b98302985d9d54599ea8ea2e01dc2503c468d58
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210223"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2 接口

用作 ICorDebugModule 接口的逻辑扩展。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ApplyChanges 方法](icordebugmodule2-applychanges-method.md)|将元数据中的更改和 Microsoft 中间语言（MSIL）代码的更改应用到正在运行的进程。|  
|[GetJITCompilerFlags 方法](icordebugmodule2-getjitcompilerflags-method.md)|获取用于控制此的实时（JIT）编译的标志 `ICorDebugModule2` 。|  
|[ResolveAssembly 方法](icordebugmodule2-resolveassembly-method.md)|解析指定的元数据标记所引用的程序集。|  
|[SetJITCompilerFlags 方法](icordebugmodule2-setjitcompilerflags-method.md)|设置控制此的 JIT 编译的标志 `ICorDebugModule2` 。|  
|[SetJMCStatus 方法](icordebugmodule2-setjmcstatus-method.md)|将此中所有类的所有方法的仅我的代码（JMC）状态设置 `ICorDebugModule2` 为指定的值（数组中的所有方法除外 `pTokens` ，将其设置为相反的值）。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](debugging-interfaces.md)
