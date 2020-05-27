---
title: CorCheckDuplicatesFor 枚举
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 2985c419b25b8bf76df8fee0f0f37ba9ebee3df7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007892"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="39bd9-102">CorCheckDuplicatesFor 枚举</span><span class="sxs-lookup"><span data-stu-id="39bd9-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="39bd9-103">指定将检查重复项的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="39bd9-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="39bd9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a><span data-ttu-id="39bd9-105">成员</span><span class="sxs-lookup"><span data-stu-id="39bd9-105">Members</span></span>  
  
|<span data-ttu-id="39bd9-106">成员</span><span class="sxs-lookup"><span data-stu-id="39bd9-106">Member</span></span>|<span data-ttu-id="39bd9-107">描述</span><span class="sxs-lookup"><span data-stu-id="39bd9-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="39bd9-108">检查所有元数据标记的重复项。</span><span class="sxs-lookup"><span data-stu-id="39bd9-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="39bd9-109">未使用。</span><span class="sxs-lookup"><span data-stu-id="39bd9-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="39bd9-110">请勿检查重复项的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="39bd9-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="39bd9-111">检查标记的重复项 `mdTypeDef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="39bd9-112">检查标记的重复项 `mdInterfaceImpl` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="39bd9-113">检查标记的重复项 `mdMethodDef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="39bd9-114">检查标记的重复项 `mdTypeRef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="39bd9-115">检查标记的重复项 `mdMemberRef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="39bd9-116">检查标记的重复项 `mdCustomAttribute` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="39bd9-117">检查标记的重复项 `mdParamDef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="39bd9-118">检查标记的重复项 `mdPermission` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="39bd9-119">检查标记的重复项 `mdProperty` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="39bd9-120">检查标记的重复项 `mdEvent` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="39bd9-121">检查标记的重复项 `mdFieldDef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="39bd9-122">检查标记的重复项 `mdSignature` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="39bd9-123">检查标记的重复项 `mdModuleRef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="39bd9-124">检查标记的重复项 `mdTypeSpec` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="39bd9-125">检查标记的重复项 `mdImplMap` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="39bd9-126">检查标记的重复项 `mdAssemblyRef` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="39bd9-127">检查标记的重复项 `mdFile` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="39bd9-128">检查标记的重复项 `mdExportedType` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="39bd9-129">检查标记的重复项 `mdManifestResource` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="39bd9-130">检查标记的重复项 `mdGenericParam` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="39bd9-131">检查标记的重复项 `mdMethodSpec` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="39bd9-132">检查标记的重复项 `mdGenericParamConstraint` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="39bd9-133">检查标记的重复项 `mdAssembly` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="39bd9-134">检查、、、 `mdMemberRef` `mdTypeRef` `mdSignature` `mdTypeSpec` 和标记的重复项 `mdMethodSpec` 。</span><span class="sxs-lookup"><span data-stu-id="39bd9-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39bd9-135">要求</span><span class="sxs-lookup"><span data-stu-id="39bd9-135">Requirements</span></span>  
 <span data-ttu-id="39bd9-136">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39bd9-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39bd9-137">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="39bd9-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="39bd9-138">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39bd9-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bd9-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39bd9-139">See also</span></span>

- [<span data-ttu-id="39bd9-140">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="39bd9-140">Metadata Enumerations</span></span>](metadata-enumerations.md)
