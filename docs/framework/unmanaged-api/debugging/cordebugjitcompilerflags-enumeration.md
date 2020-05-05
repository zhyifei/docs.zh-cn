---
title: CorDebugJITCompilerFlags 枚举
ms.date: 03/30/2017
api_name:
- CorDebugJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugJITCompilerFlags
helpviewer_keywords:
- CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type:
- apiref
ms.openlocfilehash: 8be8ce36b557831bc0997dd1c69abb924390d051
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795815"
---
# <a name="cordebugjitcompilerflags-enumeration"></a>CorDebugJITCompilerFlags 枚举
包含影响托管的实时 (JIT) 编译器的行为的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|指定编译器应跟踪编译数据，并允许优化。|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|指定编译器应跟踪编译数据，但禁用优化。|  
|`CORDEBUG_JIT_ENABLE_ENC`|指定编译器应跟踪编译数据，禁用优化，并启用 "编辑并继续" 技术。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试枚举](debugging-enumerations.md)
