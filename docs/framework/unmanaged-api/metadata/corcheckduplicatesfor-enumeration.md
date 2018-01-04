---
title: "CorCheckDuplicatesFor 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCheckDuplicatesFor
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCheckDuplicatesFor
helpviewer_keywords: CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c5a9376f6d56e2a21ee474e2724ce5eff8f6f63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corcheckduplicatesfor-enumeration"></a><span data-ttu-id="dfbe3-102">CorCheckDuplicatesFor 枚举</span><span class="sxs-lookup"><span data-stu-id="dfbe3-102">CorCheckDuplicatesFor Enumeration</span></span>
<span data-ttu-id="dfbe3-103">指定将重复项检查其元数据标记。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-103">Specifies the metadata tokens that will be checked for duplicates.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfbe3-104">语法</span><span class="sxs-lookup"><span data-stu-id="dfbe3-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="dfbe3-105">成员</span><span class="sxs-lookup"><span data-stu-id="dfbe3-105">Members</span></span>  
  
|<span data-ttu-id="dfbe3-106">成员</span><span class="sxs-lookup"><span data-stu-id="dfbe3-106">Member</span></span>|<span data-ttu-id="dfbe3-107">描述</span><span class="sxs-lookup"><span data-stu-id="dfbe3-107">Description</span></span>|  
|------------|-----------------|  
|`MDDupAll`|<span data-ttu-id="dfbe3-108">请检查重复项的所有元数据标记。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-108">Check all metadata tokens for duplicates.</span></span>|  
|`MDDupENC`|<span data-ttu-id="dfbe3-109">未使用。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-109">Not used.</span></span>|  
|`MDNoDupChecks`|<span data-ttu-id="dfbe3-110">请检查重复项的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-110">Do not check metadata tokens for duplicates.</span></span>|  
|`MDDupTypeDef`|<span data-ttu-id="dfbe3-111">检查重复项的`mdTypeDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-111">Check for duplicates of `mdTypeDef` tokens.</span></span>|  
|`MDDupInterfaceImpl`|<span data-ttu-id="dfbe3-112">检查重复项的`mdInterfaceImpl`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-112">Check for duplicates of `mdInterfaceImpl` tokens.</span></span>|  
|`MDDupMethodDef`|<span data-ttu-id="dfbe3-113">检查重复项的`mdMethodDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-113">Check for duplicates of `mdMethodDef` tokens.</span></span>|  
|`MDDupTypeRef`|<span data-ttu-id="dfbe3-114">检查重复项的`mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-114">Check for duplicates of `mdTypeRef` tokens.</span></span>|  
|`MDDupMemberRef`|<span data-ttu-id="dfbe3-115">检查重复项的`mdMemberRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-115">Check for duplicates of `mdMemberRef` tokens.</span></span>|  
|`MDDupCustomAttribute`|<span data-ttu-id="dfbe3-116">检查重复项的`mdCustomAttribute`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-116">Check for duplicates of `mdCustomAttribute` tokens.</span></span>|  
|`MDDupParamDef`|<span data-ttu-id="dfbe3-117">检查重复项的`mdParamDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-117">Check for duplicates of `mdParamDef` tokens.</span></span>|  
|`MDDupPermission`|<span data-ttu-id="dfbe3-118">检查重复项的`mdPermission`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-118">Check for duplicates of `mdPermission` tokens.</span></span>|  
|`MDDupProperty`|<span data-ttu-id="dfbe3-119">检查重复项的`mdProperty`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-119">Check for duplicates of `mdProperty` tokens.</span></span>|  
|`MDDupEvent`|<span data-ttu-id="dfbe3-120">检查重复项的`mdEvent`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-120">Check for duplicates of `mdEvent` tokens.</span></span>|  
|`MDDupFieldDef`|<span data-ttu-id="dfbe3-121">检查重复项的`mdFieldDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-121">Check for duplicates of `mdFieldDef` tokens.</span></span>|  
|`MDDupSignature`|<span data-ttu-id="dfbe3-122">检查重复项的`mdSignature`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-122">Check for duplicates of `mdSignature` tokens.</span></span>|  
|`MDDupModuleRef`|<span data-ttu-id="dfbe3-123">检查重复项的`mdModuleRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-123">Check for duplicates of `mdModuleRef` tokens.</span></span>|  
|`MDDupTypeSpec`|<span data-ttu-id="dfbe3-124">检查重复项的`mdTypeSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-124">Check for duplicates of `mdTypeSpec` tokens.</span></span>|  
|`MDDupImplMap`|<span data-ttu-id="dfbe3-125">检查重复项的`mdImplMap`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-125">Check for duplicates of `mdImplMap` tokens.</span></span>|  
|`MDDupAssemblyRef`|<span data-ttu-id="dfbe3-126">检查重复项的`mdAssemblyRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-126">Check for duplicates of `mdAssemblyRef` tokens.</span></span>|  
|`MDDupFile`|<span data-ttu-id="dfbe3-127">检查重复项的`mdFile`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-127">Check for duplicates of `mdFile` tokens.</span></span>|  
|`MDDupExportedType`|<span data-ttu-id="dfbe3-128">检查重复项的`mdExportedType`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-128">Check for duplicates of `mdExportedType` tokens.</span></span>|  
|`MDDupManifestResource`|<span data-ttu-id="dfbe3-129">检查重复项的`mdManifestResource`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-129">Check for duplicates of `mdManifestResource` tokens.</span></span>|  
|`MDDupGenericParam`|<span data-ttu-id="dfbe3-130">检查重复项的`mdGenericParam`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-130">Check for duplicates of `mdGenericParam` tokens.</span></span>|  
|`MDDupMethodSpec`|<span data-ttu-id="dfbe3-131">检查重复项的`mdMethodSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-131">Check for duplicates of `mdMethodSpec` tokens.</span></span>|  
|`MDDupGenericParamConstraint`|<span data-ttu-id="dfbe3-132">检查重复项的`mdGenericParamConstraint`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-132">Check for duplicates of `mdGenericParamConstraint` tokens.</span></span>|  
|`MDDupAssembly`|<span data-ttu-id="dfbe3-133">检查重复项的`mdAssembly`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-133">Check for duplicates of `mdAssembly` tokens.</span></span>|  
|`MDDupDefault`|<span data-ttu-id="dfbe3-134">检查重复项的`mdMemberRef`， `mdTypeRef`， `mdSignature`， `mdTypeSpec`，和`mdMethodSpec`令牌。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-134">Check for duplicates of `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, and `mdMethodSpec` tokens.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dfbe3-135">惠?</span><span class="sxs-lookup"><span data-stu-id="dfbe3-135">Requirements</span></span>  
 <span data-ttu-id="dfbe3-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dfbe3-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfbe3-137">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="dfbe3-137">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="dfbe3-138">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfbe3-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfbe3-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfbe3-139">See Also</span></span>  
 [<span data-ttu-id="dfbe3-140">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="dfbe3-140">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
