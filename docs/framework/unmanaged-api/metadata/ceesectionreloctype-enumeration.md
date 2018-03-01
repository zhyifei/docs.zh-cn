---
title: "CeeSectionRelocType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d257778a9a05e2654d7f91c0205424d001f5ae3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="06ecb-102">CeeSectionRelocType 枚举</span><span class="sxs-lookup"><span data-stu-id="06ecb-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="06ecb-103">提供值来影响的一种`reloc`指令发出对的调用中[iceegen:: Addsectionreloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)。</span><span class="sxs-lookup"><span data-stu-id="06ecb-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ecb-104">语法</span><span class="sxs-lookup"><span data-stu-id="06ecb-104">Syntax</span></span>  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a><span data-ttu-id="06ecb-105">成员</span><span class="sxs-lookup"><span data-stu-id="06ecb-105">Members</span></span>  
  
|<span data-ttu-id="06ecb-106">成员</span><span class="sxs-lookup"><span data-stu-id="06ecb-106">Member</span></span>|<span data-ttu-id="06ecb-107">描述</span><span class="sxs-lookup"><span data-stu-id="06ecb-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="06ecb-108">生成仅部分相对`reloc`、 发送到.reloc 节执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="06ecb-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="06ecb-109">生成`reloc`指针大小的位置。</span><span class="sxs-lookup"><span data-stu-id="06ecb-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="06ecb-110">这将转换为 BASED_HIGHLOW 或 BASED_DIR64 因平台而异。</span><span class="sxs-lookup"><span data-stu-id="06ecb-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="06ecb-111">生成`reloc`前几位的 32 位数字，其中.reloc 表中的下一个单词中包含的底部 16 位的 16 位。</span><span class="sxs-lookup"><span data-stu-id="06ecb-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="06ecb-112">生成令牌映射重定位，发送到.reloc 节执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="06ecb-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="06ecb-113">指示的值是相对地址修正。</span><span class="sxs-lookup"><span data-stu-id="06ecb-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="06ecb-114">生成仅部分相对`reloc`、 发送到.reloc 节执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="06ecb-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="06ecb-115">这`reloc`是相对于文件位置的部分中，该节的虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="06ecb-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="06ecb-116">指定代码相对地址修正。</span><span class="sxs-lookup"><span data-stu-id="06ecb-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="06ecb-117">生成`reloc`ia64 中的 64 位地址`movl`指令。</span><span class="sxs-lookup"><span data-stu-id="06ecb-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="06ecb-118">生成`reloc`针对 64 位地址。</span><span class="sxs-lookup"><span data-stu-id="06ecb-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="06ecb-119">生成`reloc`ia64 中的 25 位 PC 相对地址`br.call`指令。</span><span class="sxs-lookup"><span data-stu-id="06ecb-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="06ecb-120">生成`reloc`ia64 中的 64 位 PC 相对地址`brl.call`指令。</span><span class="sxs-lookup"><span data-stu-id="06ecb-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="06ecb-121">生成 30 位的部分相对`reloc`，用于标记的指针值。</span><span class="sxs-lookup"><span data-stu-id="06ecb-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="06ecb-122">要帮助确保任何添加到此枚举的一个 sentinel 值反映到内部`reloc`名称数组。</span><span class="sxs-lookup"><span data-stu-id="06ecb-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="06ecb-123">指定不发出基类`reloc`。</span><span class="sxs-lookup"><span data-stu-id="06ecb-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="06ecb-124">一个值，该值的内存的前修正内容一个指针，而不是部分偏移量。</span><span class="sxs-lookup"><span data-stu-id="06ecb-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06ecb-125">惠?</span><span class="sxs-lookup"><span data-stu-id="06ecb-125">Requirements</span></span>  
 <span data-ttu-id="06ecb-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06ecb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ecb-127">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="06ecb-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06ecb-128">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="06ecb-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06ecb-129">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ecb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ecb-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="06ecb-130">See Also</span></span>  
 [<span data-ttu-id="06ecb-131">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="06ecb-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="06ecb-132">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="06ecb-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [<span data-ttu-id="06ecb-133">AddSectionReloc 方法</span><span class="sxs-lookup"><span data-stu-id="06ecb-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
