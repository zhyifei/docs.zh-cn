---
title: "CorOpenFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorOpenFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorOpenFlags
helpviewer_keywords: CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 39645de71913baeaa39524e1cae081de9cac3442
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="8a6b0-102">CorOpenFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="8a6b0-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="8a6b0-103">包含一些标志值，用于控制打开清单文件时的元数据行为。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a6b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="8a6b0-104">Syntax</span></span>  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8a6b0-105">成员</span><span class="sxs-lookup"><span data-stu-id="8a6b0-105">Members</span></span>  
  
|<span data-ttu-id="8a6b0-106">成员</span><span class="sxs-lookup"><span data-stu-id="8a6b0-106">Member</span></span>|<span data-ttu-id="8a6b0-107">描述</span><span class="sxs-lookup"><span data-stu-id="8a6b0-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="8a6b0-108">指示该文件应在只读状态下打开。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="8a6b0-109">指示该文件应在可写入状态下打开。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="8a6b0-110">如果在打开 .winmd 文件时使用 `ofWrite` 标志，则你还应该传递 `ofNoTransform` 标志。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="8a6b0-111">读写操作的掩码。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="8a6b0-112">指示应将该文件读入内存。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="8a6b0-113">元数据应保持自己的副本。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="8a6b0-114">已过时。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-114">Obsolete.</span></span> <span data-ttu-id="8a6b0-115">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="8a6b0-116">已过时。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-116">Obsolete.</span></span> <span data-ttu-id="8a6b0-117">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="8a6b0-118">指示应打开文件进行读取，并且调用`QueryInterface`为[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)无法进行。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="8a6b0-119">指示已分配内存的使用调用[CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c)和由元数据会被释放。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="8a6b0-120">已过时。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-120">Obsolete.</span></span> <span data-ttu-id="8a6b0-121">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="8a6b0-122">指示应该禁用 .winmd 文件的自动转换。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="8a6b0-123">也就是说，应该禁用从 Windows 运行时类型到 .NET Framework 类型的投影。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="8a6b0-124">有关详细信息，请参阅[.NET 和 Windows 运行时的内涵](http://msdn.microsoft.com/magazine/jj651569.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-124">For more information, see [Underneath the Hood with .NET and the Windows Runtime](http://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="8a6b0-125">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="8a6b0-126">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="8a6b0-127">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a6b0-128">惠?</span><span class="sxs-lookup"><span data-stu-id="8a6b0-128">Requirements</span></span>  
 <span data-ttu-id="8a6b0-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8a6b0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a6b0-130">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8a6b0-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8a6b0-131">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a6b0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6b0-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a6b0-132">See Also</span></span>  
 [<span data-ttu-id="8a6b0-133">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="8a6b0-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
