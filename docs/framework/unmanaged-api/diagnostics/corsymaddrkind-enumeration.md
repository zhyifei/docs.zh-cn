---
title: CorSymAddrKind 枚举
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
ms.openlocfilehash: 5991b0abaedabe2337cd754c7bd19f96c5e9b685
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420612"
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind 枚举
指示内存地址的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|指示 Microsoft 中间语言（MSIL）本地变量或参数索引。|  
|`ADDR_NATIVE_RVA`|指示模块中的相对虚拟地址。|  
|`ADDR_NATIVE_REGISTER`|指示 CPU 寄存器。|  
|`ADDR_NATIVE_REGREL`|指示第一个地址是寄存器，第二个地址是偏移量。|  
|`ADDR_NATIVE_OFFSET`|指示与基址的偏移量。|  
|`ADDR_NATIVE_REGREG`|指示第一个地址为寄存器的低部分，第二个地址为高部分。|  
|`ADDR_NATIVE_REGSTK`|指示第一个地址是寄存器的低部分，第二个是高部分，第三个是偏移量。|  
|`ADDR_NATIVE_STKREG`|指示第一个地址为寄存器，第二个为偏移量，第三个是寄存器的高位部分。|  
|`ADDR_BITFIELD`|指示第一个地址是字段的开头，第二个地址是字段长度。|  
|`ADDR_NATIVE_ISECTOFFSET`|指示第一个地址为节，第二个地址为偏移量。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区枚举](diagnostics-symbol-store-enumerations.md)
