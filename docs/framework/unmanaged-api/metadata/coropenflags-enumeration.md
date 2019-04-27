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
ms.openlocfilehash: 55934ef08b10764bb705d7c166621ec7cfcadd0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992675"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="f85f5-102">CorOpenFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="f85f5-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="f85f5-103">包含一些标志值，用于控制打开清单文件时的元数据行为。</span><span class="sxs-lookup"><span data-stu-id="f85f5-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85f5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f85f5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f85f5-105">成员</span><span class="sxs-lookup"><span data-stu-id="f85f5-105">Members</span></span>  
  
|<span data-ttu-id="f85f5-106">成员</span><span class="sxs-lookup"><span data-stu-id="f85f5-106">Member</span></span>|<span data-ttu-id="f85f5-107">描述</span><span class="sxs-lookup"><span data-stu-id="f85f5-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="f85f5-108">指示该文件应在只读状态下打开。</span><span class="sxs-lookup"><span data-stu-id="f85f5-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="f85f5-109">指示该文件应在可写入状态下打开。</span><span class="sxs-lookup"><span data-stu-id="f85f5-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="f85f5-110">如果在打开 .winmd 文件时使用 `ofWrite` 标志，则你还应该传递 `ofNoTransform` 标志。</span><span class="sxs-lookup"><span data-stu-id="f85f5-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="f85f5-111">读写操作的掩码。</span><span class="sxs-lookup"><span data-stu-id="f85f5-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="f85f5-112">指示应将该文件读入内存。</span><span class="sxs-lookup"><span data-stu-id="f85f5-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="f85f5-113">元数据应保持自己的副本。</span><span class="sxs-lookup"><span data-stu-id="f85f5-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="f85f5-114">已过时。</span><span class="sxs-lookup"><span data-stu-id="f85f5-114">Obsolete.</span></span> <span data-ttu-id="f85f5-115">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="f85f5-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="f85f5-116">已过时。</span><span class="sxs-lookup"><span data-stu-id="f85f5-116">Obsolete.</span></span> <span data-ttu-id="f85f5-117">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="f85f5-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="f85f5-118">指示应打开文件进行读取，并且调用`QueryInterface`有关[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)无法进行。</span><span class="sxs-lookup"><span data-stu-id="f85f5-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="f85f5-119">指示内存被分配通过调用[CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) ，将释放由元数据。</span><span class="sxs-lookup"><span data-stu-id="f85f5-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="f85f5-120">已过时。</span><span class="sxs-lookup"><span data-stu-id="f85f5-120">Obsolete.</span></span> <span data-ttu-id="f85f5-121">将忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="f85f5-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="f85f5-122">指示应该禁用 .winmd 文件的自动转换。</span><span class="sxs-lookup"><span data-stu-id="f85f5-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="f85f5-123">也就是说，应该禁用从 Windows 运行时类型到 .NET Framework 类型的投影。</span><span class="sxs-lookup"><span data-stu-id="f85f5-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="f85f5-124">有关详细信息，请参阅[Windows 运行时和 CLR-使用.NET 和 Windows 运行时其下方后台](https://msdn.microsoft.com/magazine/jj651569.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f85f5-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](https://msdn.microsoft.com/magazine/jj651569.aspx).</span></span>|  
|`ofReserved1`|<span data-ttu-id="f85f5-125">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="f85f5-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="f85f5-126">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="f85f5-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="f85f5-127">保留以供内部使用。</span><span class="sxs-lookup"><span data-stu-id="f85f5-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f85f5-128">要求</span><span class="sxs-lookup"><span data-stu-id="f85f5-128">Requirements</span></span>  
 <span data-ttu-id="f85f5-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f85f5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f85f5-130">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f85f5-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f85f5-131">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f85f5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85f5-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="f85f5-132">See also</span></span>

- [<span data-ttu-id="f85f5-133">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="f85f5-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
