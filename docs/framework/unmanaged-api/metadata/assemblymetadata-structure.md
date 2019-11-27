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
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444269"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="1b5e8-102">ASSEMBLYMETADATA 结构</span><span class="sxs-lookup"><span data-stu-id="1b5e8-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="1b5e8-103">包含有关被引用程序集的信息，包括其版本及其对区域设置、处理器和操作系统的支持级别。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="1b5e8-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="1b5e8-105">Members</span><span class="sxs-lookup"><span data-stu-id="1b5e8-105">Members</span></span>  
  
|<span data-ttu-id="1b5e8-106">成员</span><span class="sxs-lookup"><span data-stu-id="1b5e8-106">Member</span></span>|<span data-ttu-id="1b5e8-107">说明</span><span class="sxs-lookup"><span data-stu-id="1b5e8-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="1b5e8-108">引用的程序集的主版本号。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="1b5e8-109">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-109">This value cannot be zero.</span></span> <span data-ttu-id="1b5e8-110">如果设置了 `usMajorVersion` 的所有位，则不指定主版本。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="1b5e8-111">所引用程序集的次版本号。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="1b5e8-112">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-112">This value cannot be zero.</span></span> <span data-ttu-id="1b5e8-113">如果设置了 `usMinorVersion` 的所有位，则不指定次版本。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="1b5e8-114">引用的程序集的生成号。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="1b5e8-115">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-115">This value cannot be zero.</span></span> <span data-ttu-id="1b5e8-116">如果设置了 `usBuildNumber` 的所有位，则不指定内部版本号。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="1b5e8-117">引用的程序集的修订号。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="1b5e8-118">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-118">This value cannot be zero.</span></span> <span data-ttu-id="1b5e8-119">如果设置了 `usRevisionNumber` 的所有位，则不指定修订号。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="1b5e8-120">符合 RFC1766 规范（由分号分隔）的区域设置名称的列表，指定被引用程序集支持的区域设置。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="1b5e8-121">空值表示区域设置独立性。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-121">A null value indicates locale independence.</span></span> <span data-ttu-id="1b5e8-122">**注意：** 在 .NET Framework 版本1.0 中，不能指定多个区域设置。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="1b5e8-123">`szLocale`的大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="1b5e8-124">Winnt 中定义的标识符的数组，适用于所引用的程序集所支持的处理器类型。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="1b5e8-125">空值表示处理器独立性。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="1b5e8-126">`rdwProcessor` 数组的长度。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="1b5e8-127">指定被引用的程序集支持的操作系统的[OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)实例的数组。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="1b5e8-128">NULL 值指示与操作系统无关。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="1b5e8-129">`rOS` 数组的长度。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b5e8-130">要求</span><span class="sxs-lookup"><span data-stu-id="1b5e8-130">Requirements</span></span>  
 <span data-ttu-id="1b5e8-131">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b5e8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b5e8-132">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="1b5e8-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b5e8-133">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1b5e8-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b5e8-134">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b5e8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5e8-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b5e8-135">See also</span></span>

- [<span data-ttu-id="1b5e8-136">元数据结构</span><span class="sxs-lookup"><span data-stu-id="1b5e8-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="1b5e8-137">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="1b5e8-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="1b5e8-138">OSINFO 结构</span><span class="sxs-lookup"><span data-stu-id="1b5e8-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
