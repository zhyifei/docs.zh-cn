---
title: IMetaDataDispenser 接口
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: b7ce76c22e7188117bddd9e4f328e323f6742685
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436225"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="a6c8b-102">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="a6c8b-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="a6c8b-103">提供创建新的元数据范围或打开现有元数据范围的方法。</span><span class="sxs-lookup"><span data-stu-id="a6c8b-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6c8b-104">方法</span><span class="sxs-lookup"><span data-stu-id="a6c8b-104">Methods</span></span>  
  
|<span data-ttu-id="a6c8b-105">方法</span><span class="sxs-lookup"><span data-stu-id="a6c8b-105">Method</span></span>|<span data-ttu-id="a6c8b-106">说明</span><span class="sxs-lookup"><span data-stu-id="a6c8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6c8b-107">DefineScope 方法</span><span class="sxs-lookup"><span data-stu-id="a6c8b-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="a6c8b-108">在内存中创建新的区域，您可以在其中创建新的元数据。</span><span class="sxs-lookup"><span data-stu-id="a6c8b-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="a6c8b-109">OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="a6c8b-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="a6c8b-110">打开现有的磁盘上的文件，并将其元数据映射到内存。</span><span class="sxs-lookup"><span data-stu-id="a6c8b-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="a6c8b-111">OpenScopeOnMemory 方法</span><span class="sxs-lookup"><span data-stu-id="a6c8b-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="a6c8b-112">打开包含现有元数据的内存区域。</span><span class="sxs-lookup"><span data-stu-id="a6c8b-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="a6c8b-113">也就是说，此方法将打开一个指定的内存区域，其中的现有数据将被视为元数据。</span><span class="sxs-lookup"><span data-stu-id="a6c8b-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6c8b-114">要求</span><span class="sxs-lookup"><span data-stu-id="a6c8b-114">Requirements</span></span>  
 <span data-ttu-id="a6c8b-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6c8b-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6c8b-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a6c8b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6c8b-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a6c8b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6c8b-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6c8b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c8b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c8b-119">See also</span></span>

- [<span data-ttu-id="a6c8b-120">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="a6c8b-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="a6c8b-121">元数据接口</span><span class="sxs-lookup"><span data-stu-id="a6c8b-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
