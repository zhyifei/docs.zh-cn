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
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176183"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="66153-102">CorCheckDuplicatesFor 枚举</span><span class="sxs-lookup"><span data-stu-id="66153-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="66153-103">指定将检查重复项的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="66153-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66153-104">语法</span><span class="sxs-lookup"><span data-stu-id="66153-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="66153-105">成员</span><span class="sxs-lookup"><span data-stu-id="66153-105">Members</span></span>  
  
|<span data-ttu-id="66153-106">成员</span><span class="sxs-lookup"><span data-stu-id="66153-106">Member</span></span>|<span data-ttu-id="66153-107">说明</span><span class="sxs-lookup"><span data-stu-id="66153-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="66153-108">检查所有元数据令牌的重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="66153-109">未使用。</span><span class="sxs-lookup"><span data-stu-id="66153-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="66153-110">不要检查元数据令牌的重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="66153-111">检查令牌的`mdTypeDef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="66153-112">检查令牌的`mdInterfaceImpl`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="66153-113">检查令牌的`mdMethodDef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="66153-114">检查令牌的`mdTypeRef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="66153-115">检查令牌的`mdMemberRef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="66153-116">检查令牌的`mdCustomAttribute`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="66153-117">检查令牌的`mdParamDef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="66153-118">检查令牌的`mdPermission`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="66153-119">检查令牌的`mdProperty`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="66153-120">检查令牌的`mdEvent`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="66153-121">检查令牌的`mdFieldDef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="66153-122">检查令牌的`mdSignature`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="66153-123">检查令牌的`mdModuleRef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="66153-124">检查令牌的`mdTypeSpec`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="66153-125">检查令牌的`mdImplMap`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="66153-126">检查令牌的`mdAssemblyRef`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="66153-127">检查令牌的`mdFile`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="66153-128">检查令牌的`mdExportedType`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="66153-129">检查令牌的`mdManifestResource`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="66153-130">检查令牌的`mdGenericParam`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="66153-131">检查令牌的`mdMethodSpec`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="66153-132">检查令牌的`mdGenericParamConstraint`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="66153-133">检查令牌的`mdAssembly`重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="66153-134">检查`mdMemberRef`、、、`mdTypeRef``mdSignature``mdTypeSpec`和`mdMethodSpec`令牌的重复项。</span><span class="sxs-lookup"><span data-stu-id="66153-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66153-135">要求</span><span class="sxs-lookup"><span data-stu-id="66153-135">Requirements</span></span>  
 <span data-ttu-id="66153-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="66153-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66153-137">**标题：** 科尔赫德</span><span class="sxs-lookup"><span data-stu-id="66153-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="66153-138">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66153-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66153-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66153-139">See also</span></span>

- [<span data-ttu-id="66153-140">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="66153-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
