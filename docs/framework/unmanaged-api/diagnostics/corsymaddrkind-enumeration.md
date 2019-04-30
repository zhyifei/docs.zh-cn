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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adef1010d08561c0a0fe38480fe0d2f519a80b49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993429"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="67e0f-102">CorSymAddrKind 枚举</span><span class="sxs-lookup"><span data-stu-id="67e0f-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="67e0f-103">指示内存地址的类型。</span><span class="sxs-lookup"><span data-stu-id="67e0f-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="67e0f-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="67e0f-105">成员</span><span class="sxs-lookup"><span data-stu-id="67e0f-105">Members</span></span>  
  
|<span data-ttu-id="67e0f-106">成员</span><span class="sxs-lookup"><span data-stu-id="67e0f-106">Member</span></span>|<span data-ttu-id="67e0f-107">描述</span><span class="sxs-lookup"><span data-stu-id="67e0f-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="67e0f-108">指示非 Microsoft 中间语言 (MSIL) 本地变量或参数索引。</span><span class="sxs-lookup"><span data-stu-id="67e0f-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="67e0f-109">指示模块中的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="67e0f-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="67e0f-110">指示 CPU 寄存器。</span><span class="sxs-lookup"><span data-stu-id="67e0f-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="67e0f-111">指示第一个地址是寄存器和第二个地址是偏移量。</span><span class="sxs-lookup"><span data-stu-id="67e0f-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="67e0f-112">指示一个偏移的基址。</span><span class="sxs-lookup"><span data-stu-id="67e0f-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="67e0f-113">指示第一个地址是寄存器中，低部分和第二个地址是高部分。</span><span class="sxs-lookup"><span data-stu-id="67e0f-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="67e0f-114">指示第一个地址是寄存器的低部分、 第二个是高的部分中，第三个是偏移量。</span><span class="sxs-lookup"><span data-stu-id="67e0f-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="67e0f-115">指示第一个地址是寄存器，第二个是偏移量，并且第三个已注册的高部分。</span><span class="sxs-lookup"><span data-stu-id="67e0f-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="67e0f-116">指示第一个地址是一个字段的开头和第二个地址是字段长度。</span><span class="sxs-lookup"><span data-stu-id="67e0f-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="67e0f-117">指示第一个地址是部分和第二个地址是偏移量。</span><span class="sxs-lookup"><span data-stu-id="67e0f-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67e0f-118">要求</span><span class="sxs-lookup"><span data-stu-id="67e0f-118">Requirements</span></span>  
 <span data-ttu-id="67e0f-119">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="67e0f-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e0f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="67e0f-120">See also</span></span>

- [<span data-ttu-id="67e0f-121">诊断符号存储区枚举</span><span class="sxs-lookup"><span data-stu-id="67e0f-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
