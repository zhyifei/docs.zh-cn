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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d04f5589ecffbcde59a6ffbe4f3d6c5f0b1040cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074867"
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="61137-102">CorCheckDuplicatesFor 枚举</span><span class="sxs-lookup"><span data-stu-id="61137-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="61137-103">指定将检查有重复项的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61137-104">语法</span><span class="sxs-lookup"><span data-stu-id="61137-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="61137-105">成员</span><span class="sxs-lookup"><span data-stu-id="61137-105">Members</span></span>  
  
|<span data-ttu-id="61137-106">成员</span><span class="sxs-lookup"><span data-stu-id="61137-106">Member</span></span>|<span data-ttu-id="61137-107">描述</span><span class="sxs-lookup"><span data-stu-id="61137-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="61137-108">检查有重复项的所有元数据标记。</span><span class="sxs-lookup"><span data-stu-id="61137-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="61137-109">未使用。</span><span class="sxs-lookup"><span data-stu-id="61137-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="61137-110">不会检查有重复项的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="61137-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="61137-111">检查重复项的`mdTypeDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="61137-112">检查重复项的`mdInterfaceImpl`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="61137-113">检查重复项的`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="61137-114">检查重复项的`mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="61137-115">检查重复项的`mdMemberRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="61137-116">检查重复项的`mdCustomAttribute`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="61137-117">检查重复项的`mdParamDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="61137-118">检查重复项的`mdPermission`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="61137-119">检查重复项的`mdProperty`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="61137-120">检查重复项的`mdEvent`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="61137-121">检查重复项的`mdFieldDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="61137-122">检查重复项的`mdSignature`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="61137-123">检查重复项的`mdModuleRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="61137-124">检查重复项的`mdTypeSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="61137-125">检查重复项的`mdImplMap`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="61137-126">检查重复项的`mdAssemblyRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="61137-127">检查重复项的`mdFile`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="61137-128">检查重复项的`mdExportedType`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="61137-129">检查重复项的`mdManifestResource`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="61137-130">检查重复项的`mdGenericParam`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="61137-131">检查重复项的`mdMethodSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="61137-132">检查重复项的`mdGenericParamConstraint`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="61137-133">检查重复项的`mdAssembly`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="61137-134">检查重复的项`mdMemberRef`， `mdTypeRef`， `mdSignature`， `mdTypeSpec`，和`mdMethodSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="61137-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61137-135">要求</span><span class="sxs-lookup"><span data-stu-id="61137-135">Requirements</span></span>  
 <span data-ttu-id="61137-136">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61137-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61137-137">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="61137-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="61137-138">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61137-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61137-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="61137-139">See also</span></span>

- [<span data-ttu-id="61137-140">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="61137-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
