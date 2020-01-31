---
title: StackTrace_SimpleContext 结构
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: c81a5787eb06971e3d52aff5d1c1154a72564daf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790334"
---
# <a name="stacktrace_simplecontext-structure"></a>StackTrace_SimpleContext 结构
提供可用于代替完整的 `CONTEXT` 结构的简单上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`StackOffset`|堆栈指针或 x86 平台上的进入堆栈指针（ESP）。|  
|`FrameOffset`|X86 平台上的帧偏移量或 EBP 寄存器。|  
|`InstructionOffset`|指令指针，或 x86 平台上的输入指令指针（EIP）。|  
  
## <a name="remarks"></a>备注  
 因为堆栈跟踪函数通常只需要返回地址、帧偏移量和堆栈地址，所以，您可以选择使用 `SimpleContext` 结构而不是大型 `CONTEXT` 结构。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** SOS_Stacktrace。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
