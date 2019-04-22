---
title: ASSEMBLYMETADATA 结构
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f0a9b9c149c86b4d9121275aa858dfdc0cdbac7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195158"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="726fa-102">ASSEMBLYMETADATA 结构</span><span class="sxs-lookup"><span data-stu-id="726fa-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="726fa-103">包含有关所引用的程序集，包括其版本和其级别的支持的区域设置、 处理器和操作系统信息。</span><span class="sxs-lookup"><span data-stu-id="726fa-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="726fa-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="726fa-105">成员</span><span class="sxs-lookup"><span data-stu-id="726fa-105">Members</span></span>  
  
|<span data-ttu-id="726fa-106">成员</span><span class="sxs-lookup"><span data-stu-id="726fa-106">Member</span></span>|<span data-ttu-id="726fa-107">描述</span><span class="sxs-lookup"><span data-stu-id="726fa-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="726fa-108">引用的程序集的主版本号。</span><span class="sxs-lookup"><span data-stu-id="726fa-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="726fa-109">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="726fa-109">This value cannot be zero.</span></span> <span data-ttu-id="726fa-110">如果所有的位`usMajorVersion`进行设置，未指定的主版本。</span><span class="sxs-lookup"><span data-stu-id="726fa-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="726fa-111">引用的程序集的次版本号。</span><span class="sxs-lookup"><span data-stu-id="726fa-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="726fa-112">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="726fa-112">This value cannot be zero.</span></span> <span data-ttu-id="726fa-113">如果所有的位`usMinorVersion`进行设置，未指定的次版本。</span><span class="sxs-lookup"><span data-stu-id="726fa-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="726fa-114">引用的程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="726fa-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="726fa-115">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="726fa-115">This value cannot be zero.</span></span> <span data-ttu-id="726fa-116">如果所有的位`usBuildNumber`进行设置，未指定生成号。</span><span class="sxs-lookup"><span data-stu-id="726fa-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="726fa-117">引用的程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="726fa-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="726fa-118">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="726fa-118">This value cannot be zero.</span></span> <span data-ttu-id="726fa-119">如果所有的位`usRevisionNumber`进行设置，未指定的修订号。</span><span class="sxs-lookup"><span data-stu-id="726fa-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="726fa-120">符合 RFC1766 规范，指定引用程序集支持的区域设置之间用分号分隔的区域设置名称的列表。</span><span class="sxs-lookup"><span data-stu-id="726fa-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="726fa-121">Null 值表示区域设置独立性。</span><span class="sxs-lookup"><span data-stu-id="726fa-121">A null value indicates locale independence.</span></span> <span data-ttu-id="726fa-122">**注意：** 在.NET Framework 版本 1.0 不能指定多个区域设置中。</span><span class="sxs-lookup"><span data-stu-id="726fa-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="726fa-123">在宽字符为单位的大小`szLocale`。</span><span class="sxs-lookup"><span data-stu-id="726fa-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="726fa-124">标识符，如在 Winnt.h 中定义引用的程序集支持的处理器类型的数组。</span><span class="sxs-lookup"><span data-stu-id="726fa-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="726fa-125">NULL 值指示处理器独立性。</span><span class="sxs-lookup"><span data-stu-id="726fa-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="726fa-126">长度`rdwProcessor`数组。</span><span class="sxs-lookup"><span data-stu-id="726fa-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="726fa-127">一个数组[OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)指定引用的程序集支持的操作系统的实例。</span><span class="sxs-lookup"><span data-stu-id="726fa-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="726fa-128">NULL 值表示操作系统独立性。</span><span class="sxs-lookup"><span data-stu-id="726fa-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="726fa-129">长度`rOS`数组。</span><span class="sxs-lookup"><span data-stu-id="726fa-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="726fa-130">要求</span><span class="sxs-lookup"><span data-stu-id="726fa-130">Requirements</span></span>  
 <span data-ttu-id="726fa-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="726fa-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726fa-132">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="726fa-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="726fa-133">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="726fa-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="726fa-134">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726fa-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726fa-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="726fa-135">See also</span></span>

- [<span data-ttu-id="726fa-136">元数据结构</span><span class="sxs-lookup"><span data-stu-id="726fa-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="726fa-137">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="726fa-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="726fa-138">OSINFO 结构</span><span class="sxs-lookup"><span data-stu-id="726fa-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
