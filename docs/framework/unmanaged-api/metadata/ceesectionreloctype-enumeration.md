---
title: CeeSectionRelocType 枚举
ms.date: 03/30/2017
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
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176209"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="47381-102">CeeSectionRelocType 枚举</span><span class="sxs-lookup"><span data-stu-id="47381-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="47381-103">提供值以影响调用 ICeeGen 时发出的`reloc`指令类型[：：AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)。</span><span class="sxs-lookup"><span data-stu-id="47381-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47381-104">语法</span><span class="sxs-lookup"><span data-stu-id="47381-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="47381-105">成员</span><span class="sxs-lookup"><span data-stu-id="47381-105">Members</span></span>  
  
|<span data-ttu-id="47381-106">成员</span><span class="sxs-lookup"><span data-stu-id="47381-106">Member</span></span>|<span data-ttu-id="47381-107">说明</span><span class="sxs-lookup"><span data-stu-id="47381-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="47381-108">仅生成与节相关的`reloc`，不会将任何内容发送到 .reloc 节。</span><span class="sxs-lookup"><span data-stu-id="47381-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="47381-109">为指针`reloc`大小的位置生成 。</span><span class="sxs-lookup"><span data-stu-id="47381-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="47381-110">根据平台的不同，这转换为BASED_HIGHLOW或BASED_DIR64。</span><span class="sxs-lookup"><span data-stu-id="47381-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="47381-111">为`reloc`32 位数字的前 16 位生成 一个，其中底部 16 位包含在 .reloc 表中的下一个单词中。</span><span class="sxs-lookup"><span data-stu-id="47381-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="47381-112">生成令牌映射重新定位，不向 .reloc 部分发送任何内容。</span><span class="sxs-lookup"><span data-stu-id="47381-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="47381-113">指示该值是相对地址修复。</span><span class="sxs-lookup"><span data-stu-id="47381-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="47381-114">仅生成与节相关的`reloc`，不会将任何内容发送到 .reloc 节。</span><span class="sxs-lookup"><span data-stu-id="47381-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="47381-115">这是`reloc`相对于节的文件位置，而不是节的虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="47381-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="47381-116">指定与代码相关的地址修复。</span><span class="sxs-lookup"><span data-stu-id="47381-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="47381-117">在`reloc`ia64 指令中为 64`movl`位地址生成 。</span><span class="sxs-lookup"><span data-stu-id="47381-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="47381-118">为`reloc`64 位地址生成 。</span><span class="sxs-lookup"><span data-stu-id="47381-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="47381-119">在`reloc`ia64`br.call`指令中为 25 位 PC 相关地址生成 。</span><span class="sxs-lookup"><span data-stu-id="47381-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="47381-120">在`reloc`ia64`brl.call`指令中为 64 位 PC 相关地址生成 。</span><span class="sxs-lookup"><span data-stu-id="47381-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="47381-121">生成 30 位节相对`reloc`， 用于标记的指针值。</span><span class="sxs-lookup"><span data-stu-id="47381-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="47381-122">一个哨点值，可帮助确保此枚举的任何添加都反映到内部`reloc`名称数组。</span><span class="sxs-lookup"><span data-stu-id="47381-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="47381-123">指定不发出基`reloc`。</span><span class="sxs-lookup"><span data-stu-id="47381-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="47381-124">指示内存的预修复内容是指针而不是节偏移量的值。</span><span class="sxs-lookup"><span data-stu-id="47381-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47381-125">要求</span><span class="sxs-lookup"><span data-stu-id="47381-125">Requirements</span></span>  
 <span data-ttu-id="47381-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47381-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47381-127">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="47381-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47381-128">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="47381-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47381-129">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47381-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47381-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47381-130">See also</span></span>

- [<span data-ttu-id="47381-131">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="47381-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="47381-132">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="47381-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="47381-133">AddSectionReloc 方法</span><span class="sxs-lookup"><span data-stu-id="47381-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
