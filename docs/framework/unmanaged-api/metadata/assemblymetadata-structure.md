---
title: "ASSEMBLYMETADATA 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLYMETADATA
api_location: mscoree.dll
api_type: COM
f1_keywords: ASSEMBLYMETADATA
helpviewer_keywords: ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 819510c14bd67e7fcc739a19ea945f16b2a66c9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="617a3-102">ASSEMBLYMETADATA 结构</span><span class="sxs-lookup"><span data-stu-id="617a3-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="617a3-103">包含有关所引用的程序集，包括其版本和其级别的支持的区域设置、 处理器和操作系统信息。</span><span class="sxs-lookup"><span data-stu-id="617a3-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="617a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="617a3-104">Syntax</span></span>  
  
```  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="617a3-105">成员</span><span class="sxs-lookup"><span data-stu-id="617a3-105">Members</span></span>  
  
|<span data-ttu-id="617a3-106">成员</span><span class="sxs-lookup"><span data-stu-id="617a3-106">Member</span></span>|<span data-ttu-id="617a3-107">描述</span><span class="sxs-lookup"><span data-stu-id="617a3-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="617a3-108">主版本号，引用程序集。</span><span class="sxs-lookup"><span data-stu-id="617a3-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="617a3-109">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="617a3-109">This value cannot be zero.</span></span> <span data-ttu-id="617a3-110">如果所有的位`usMajorVersion`的设置，未指定的主版本。</span><span class="sxs-lookup"><span data-stu-id="617a3-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="617a3-111">引用的程序集的次版本号。</span><span class="sxs-lookup"><span data-stu-id="617a3-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="617a3-112">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="617a3-112">This value cannot be zero.</span></span> <span data-ttu-id="617a3-113">如果所有的位`usMinorVersion`的设置，未指定的次版本。</span><span class="sxs-lookup"><span data-stu-id="617a3-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="617a3-114">引用的程序集的生成号。</span><span class="sxs-lookup"><span data-stu-id="617a3-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="617a3-115">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="617a3-115">This value cannot be zero.</span></span> <span data-ttu-id="617a3-116">如果所有的位`usBuildNumber`的设置，未指定的生成号。</span><span class="sxs-lookup"><span data-stu-id="617a3-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="617a3-117">引用的程序集修订号。</span><span class="sxs-lookup"><span data-stu-id="617a3-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="617a3-118">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="617a3-118">This value cannot be zero.</span></span> <span data-ttu-id="617a3-119">如果所有的位`usRevisionNumber`的设置，未指定修订号。</span><span class="sxs-lookup"><span data-stu-id="617a3-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="617a3-120">符合 RFC1766 规范中，由分号分隔，指定所引用的程序集支持的区域设置的区域设置名称的列表。</span><span class="sxs-lookup"><span data-stu-id="617a3-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="617a3-121">Null 值表示区域设置独立性。</span><span class="sxs-lookup"><span data-stu-id="617a3-121">A null value indicates locale independence.</span></span> <span data-ttu-id="617a3-122">**注意：** .NET Framework 版本 1.0 不能指定多个区域设置中。</span><span class="sxs-lookup"><span data-stu-id="617a3-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="617a3-123">在宽字符为单位的大小`szLocale`。</span><span class="sxs-lookup"><span data-stu-id="617a3-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="617a3-124">标识符，如 Winnt.h 中的定义被引用程序集支持的处理器类型的数组。</span><span class="sxs-lookup"><span data-stu-id="617a3-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="617a3-125">一个 NULL 值指示处理器独立性。</span><span class="sxs-lookup"><span data-stu-id="617a3-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="617a3-126">长度`rdwProcessor`数组。</span><span class="sxs-lookup"><span data-stu-id="617a3-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="617a3-127">数组[OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)指定引用的程序集支持的操作系统的实例。</span><span class="sxs-lookup"><span data-stu-id="617a3-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="617a3-128">一个 NULL 值指示操作系统独立性。</span><span class="sxs-lookup"><span data-stu-id="617a3-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="617a3-129">长度`rOS`数组。</span><span class="sxs-lookup"><span data-stu-id="617a3-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="617a3-130">惠?</span><span class="sxs-lookup"><span data-stu-id="617a3-130">Requirements</span></span>  
 <span data-ttu-id="617a3-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="617a3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="617a3-132">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="617a3-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="617a3-133">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="617a3-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="617a3-134">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="617a3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617a3-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="617a3-135">See Also</span></span>  
 [<span data-ttu-id="617a3-136">元数据结构</span><span class="sxs-lookup"><span data-stu-id="617a3-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="617a3-137">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="617a3-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="617a3-138">OSINFO 结构</span><span class="sxs-lookup"><span data-stu-id="617a3-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
