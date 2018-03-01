---
title: "IMetaDataDispenser 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 678796357b36beb26ebbf34edc713ff6f15a7c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="af920-102">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="af920-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="af920-103">提供用于创建新的元数据范围，或打开一个现有方法。</span><span class="sxs-lookup"><span data-stu-id="af920-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af920-104">方法</span><span class="sxs-lookup"><span data-stu-id="af920-104">Methods</span></span>  
  
|<span data-ttu-id="af920-105">方法</span><span class="sxs-lookup"><span data-stu-id="af920-105">Method</span></span>|<span data-ttu-id="af920-106">描述</span><span class="sxs-lookup"><span data-stu-id="af920-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af920-107">DefineScope 方法</span><span class="sxs-lookup"><span data-stu-id="af920-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="af920-108">你可以在其中创建新的元数据的内存中创建一个新的区域。</span><span class="sxs-lookup"><span data-stu-id="af920-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="af920-109">OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="af920-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="af920-110">打开一个现有的磁盘上的文件并将其元数据映射到内存。</span><span class="sxs-lookup"><span data-stu-id="af920-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="af920-111">OpenScopeOnMemory 方法</span><span class="sxs-lookup"><span data-stu-id="af920-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="af920-112">将打开一个包含现有的元数据的内存区域。</span><span class="sxs-lookup"><span data-stu-id="af920-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="af920-113">也就是说，此方法打开的现有数据视为元数据的内存的指定的区域。</span><span class="sxs-lookup"><span data-stu-id="af920-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af920-114">惠?</span><span class="sxs-lookup"><span data-stu-id="af920-114">Requirements</span></span>  
 <span data-ttu-id="af920-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af920-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af920-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af920-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af920-117">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="af920-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af920-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af920-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af920-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="af920-119">See Also</span></span>  
 [<span data-ttu-id="af920-120">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="af920-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="af920-121">元数据接口</span><span class="sxs-lookup"><span data-stu-id="af920-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
