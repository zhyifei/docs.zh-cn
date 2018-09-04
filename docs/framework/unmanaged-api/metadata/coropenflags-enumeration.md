---
title: CorOpenFlags 枚举
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c08b1f6be41de63886115e5aed6bcad901658bb5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509215"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="5a04e-102">CorOpenFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="5a04e-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="5a04e-103">包含一些标志值，用于控制打开清单文件时的元数据行为。</span><span class="sxs-lookup"><span data-stu-id="5a04e-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a04e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a04e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="5a04e-105">成员</span><span class="sxs-lookup"><span data-stu-id="5a04e-105">Members</span></span>  
  
|<span data-ttu-id="5a04e-106">成员</span><span class="sxs-lookup"><span data-stu-id="5a04e-106">Member</span></span>|<span data-ttu-id="5a04e-107">描述</span><span class="sxs-lookup"><span data-stu-id="5a04e-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="5a04e-108">指示该文件应在只读状态下打开。</span><span class="sxs-lookup"><span data-stu-id="5a04e-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="5a04e-109">指示该文件应在可写入状态下打开。</span><span class="sxs-lookup"><span data-stu-id="5a04e-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="5a04e-110">如果在打开 .winmd 文件时使用 `ofWrite` 标志，则你还应该传递 `ofNoTransform` 标志。</span><span class="sxs-lookup"><span data-stu-id="5a04e-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="5a04e-111">读写操作的掩码。</span><span class="sxs-lookup"><span data-stu-id="5a04e-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="5a04e-112">指示应将该文件读入内存。</span><span class="sxs-lookup"><span data-stu-id="5a04e-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="5a04e-113">元数据应保持自己的副本。</span><span class="sxs-lookup"><span data-stu-id="5a04e-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="5a04e-114">已过时。</span><span class="sxs-lookup"><span data-stu-id="5a04e-114">Obsolete.</span></span> <span data-ttu-id="5a04e-115">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="5a04e-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="5a04e-116">已过时。</span><span class="sxs-lookup"><span data-stu-id="5a04e-116">Obsolete.</span></span> <span data-ttu-id="5a04e-117">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="5a04e-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="5a04e-118">指示应打开文件进行读取，并且调用`QueryInterface`有关[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)无法进行。</span><span class="sxs-lookup"><span data-stu-id="5a04e-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="5a04e-119">指示内存被分配通过调用[CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) ，将释放由元数据。</span><span class="sxs-lookup"><span data-stu-id="5a04e-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="5a04e-120">已过时。</span><span class="sxs-lookup"><span data-stu-id="5a04e-120">Obsolete.</span></span> <span data-ttu-id="5a04e-121">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="5a04e-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="5a04e-122">指示应该禁用 .winmd 文件的自动转换。</span><span class="sxs-lookup"><span data-stu-id="5a04e-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="5a04e-123">也就是说，应该禁用从 Windows 运行时类型到 .NET Framework 类型的投影。</span><span class="sxs-lookup"><span data-stu-id="5a04e-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="5a04e-124">有关详细信息，请参阅[其下方底层信息使用.NET 和 Windows 运行时](https://msdn.microsoft.com/magazine/jj651569.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5a04e-124">For more information, see [Underneath the Hood with .NET and the Windows Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="5a04e-125">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="5a04e-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="5a04e-126">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="5a04e-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="5a04e-127">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="5a04e-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a04e-128">要求</span><span class="sxs-lookup"><span data-stu-id="5a04e-128">Requirements</span></span>  
 <span data-ttu-id="5a04e-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5a04e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a04e-130">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5a04e-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5a04e-131">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a04e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a04e-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a04e-132">See Also</span></span>  
 [<span data-ttu-id="5a04e-133">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="5a04e-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
