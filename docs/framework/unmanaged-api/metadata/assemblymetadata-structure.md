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
ms.openlocfilehash: 5c7211fc2523b70313a1e4d4d9d2da0dcecd1d32
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009426"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="6343d-102">ASSEMBLYMETADATA 结构</span><span class="sxs-lookup"><span data-stu-id="6343d-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="6343d-103">包含有关被引用程序集的信息，包括其版本及其对区域设置、处理器和操作系统的支持级别。</span><span class="sxs-lookup"><span data-stu-id="6343d-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6343d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6343d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6343d-105">成员</span><span class="sxs-lookup"><span data-stu-id="6343d-105">Members</span></span>  
  
|<span data-ttu-id="6343d-106">成员</span><span class="sxs-lookup"><span data-stu-id="6343d-106">Member</span></span>|<span data-ttu-id="6343d-107">描述</span><span class="sxs-lookup"><span data-stu-id="6343d-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="6343d-108">引用的程序集的主版本号。</span><span class="sxs-lookup"><span data-stu-id="6343d-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="6343d-109">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="6343d-109">This value cannot be zero.</span></span> <span data-ttu-id="6343d-110">如果设置了的所有位 `usMajorVersion` ，则不指定主版本。</span><span class="sxs-lookup"><span data-stu-id="6343d-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="6343d-111">所引用程序集的次版本号。</span><span class="sxs-lookup"><span data-stu-id="6343d-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="6343d-112">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="6343d-112">This value cannot be zero.</span></span> <span data-ttu-id="6343d-113">如果设置了的所有位 `usMinorVersion` ，则不指定次版本。</span><span class="sxs-lookup"><span data-stu-id="6343d-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="6343d-114">引用程序集的生成号。</span><span class="sxs-lookup"><span data-stu-id="6343d-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="6343d-115">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="6343d-115">This value cannot be zero.</span></span> <span data-ttu-id="6343d-116">如果设置了的所有位 `usBuildNumber` ，则不指定生成号。</span><span class="sxs-lookup"><span data-stu-id="6343d-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="6343d-117">引用的程序集的修订号。</span><span class="sxs-lookup"><span data-stu-id="6343d-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="6343d-118">此值不能为零。</span><span class="sxs-lookup"><span data-stu-id="6343d-118">This value cannot be zero.</span></span> <span data-ttu-id="6343d-119">如果设置了的所有位 `usRevisionNumber` ，则不指定修订号。</span><span class="sxs-lookup"><span data-stu-id="6343d-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="6343d-120">符合 RFC1766 规范（由分号分隔）的区域设置名称的列表，指定被引用程序集支持的区域设置。</span><span class="sxs-lookup"><span data-stu-id="6343d-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="6343d-121">空值表示区域设置独立性。</span><span class="sxs-lookup"><span data-stu-id="6343d-121">A null value indicates locale independence.</span></span> <span data-ttu-id="6343d-122">**注意：** 在 .NET Framework 版本1.0 中，不能指定多个区域设置。</span><span class="sxs-lookup"><span data-stu-id="6343d-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="6343d-123">的大小（以宽字符为大小） `szLocale` 。</span><span class="sxs-lookup"><span data-stu-id="6343d-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="6343d-124">Winnt 中定义的标识符的数组，适用于所引用的程序集所支持的处理器类型。</span><span class="sxs-lookup"><span data-stu-id="6343d-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="6343d-125">空值表示处理器独立性。</span><span class="sxs-lookup"><span data-stu-id="6343d-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="6343d-126">`rdwProcessor` 数组的长度。</span><span class="sxs-lookup"><span data-stu-id="6343d-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="6343d-127">指定被引用的程序集支持的操作系统的[OSINFO](osinfo-structure.md)实例的数组。</span><span class="sxs-lookup"><span data-stu-id="6343d-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="6343d-128">NULL 值指示与操作系统无关。</span><span class="sxs-lookup"><span data-stu-id="6343d-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="6343d-129">`rOS` 数组的长度。</span><span class="sxs-lookup"><span data-stu-id="6343d-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6343d-130">要求</span><span class="sxs-lookup"><span data-stu-id="6343d-130">Requirements</span></span>  
 <span data-ttu-id="6343d-131">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6343d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6343d-132">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="6343d-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6343d-133">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6343d-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6343d-134">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6343d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6343d-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6343d-135">See also</span></span>

- [<span data-ttu-id="6343d-136">元数据结构</span><span class="sxs-lookup"><span data-stu-id="6343d-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="6343d-137">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="6343d-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="6343d-138">OSINFO 结构</span><span class="sxs-lookup"><span data-stu-id="6343d-138">OSINFO Structure</span></span>](osinfo-structure.md)
