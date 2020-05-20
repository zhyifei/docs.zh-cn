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
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="85064-102">CorSymAddrKind 枚举</span><span class="sxs-lookup"><span data-stu-id="85064-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="85064-103">指示内存地址的类型。</span><span class="sxs-lookup"><span data-stu-id="85064-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85064-104">语法</span><span class="sxs-lookup"><span data-stu-id="85064-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="85064-105">成员</span><span class="sxs-lookup"><span data-stu-id="85064-105">Members</span></span>  
  
|<span data-ttu-id="85064-106">成员</span><span class="sxs-lookup"><span data-stu-id="85064-106">Member</span></span>|<span data-ttu-id="85064-107">描述</span><span class="sxs-lookup"><span data-stu-id="85064-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="85064-108">指示 Microsoft 中间语言（MSIL）本地变量或参数索引。</span><span class="sxs-lookup"><span data-stu-id="85064-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="85064-109">指示模块中的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="85064-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="85064-110">指示 CPU 寄存器。</span><span class="sxs-lookup"><span data-stu-id="85064-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="85064-111">指示第一个地址是寄存器，第二个地址是偏移量。</span><span class="sxs-lookup"><span data-stu-id="85064-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="85064-112">指示与基址的偏移量。</span><span class="sxs-lookup"><span data-stu-id="85064-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="85064-113">指示第一个地址为寄存器的低部分，第二个地址为高部分。</span><span class="sxs-lookup"><span data-stu-id="85064-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="85064-114">指示第一个地址是寄存器的低部分，第二个是高部分，第三个是偏移量。</span><span class="sxs-lookup"><span data-stu-id="85064-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="85064-115">指示第一个地址为寄存器，第二个为偏移量，第三个是寄存器的高位部分。</span><span class="sxs-lookup"><span data-stu-id="85064-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="85064-116">指示第一个地址是字段的开头，第二个地址是字段长度。</span><span class="sxs-lookup"><span data-stu-id="85064-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="85064-117">指示第一个地址为节，第二个地址为偏移量。</span><span class="sxs-lookup"><span data-stu-id="85064-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85064-118">要求</span><span class="sxs-lookup"><span data-stu-id="85064-118">Requirements</span></span>  
 <span data-ttu-id="85064-119">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="85064-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85064-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85064-120">See also</span></span>

- [<span data-ttu-id="85064-121">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="85064-121">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
