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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda284fc86f0a82472c59d6bab08fd4a87364723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225971"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="1c5a3-102">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="1c5a3-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="1c5a3-103">提供要创建新的元数据范围，或打开一个现有的方法。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c5a3-104">方法</span><span class="sxs-lookup"><span data-stu-id="1c5a3-104">Methods</span></span>  
  
|<span data-ttu-id="1c5a3-105">方法</span><span class="sxs-lookup"><span data-stu-id="1c5a3-105">Method</span></span>|<span data-ttu-id="1c5a3-106">描述</span><span class="sxs-lookup"><span data-stu-id="1c5a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c5a3-107">DefineScope 方法</span><span class="sxs-lookup"><span data-stu-id="1c5a3-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="1c5a3-108">您可以在其中创建新的元数据的内存中创建一个新的区域。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="1c5a3-109">OpenScope 方法</span><span class="sxs-lookup"><span data-stu-id="1c5a3-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="1c5a3-110">打开一个现有的磁盘上的文件并将其元数据映射到内存中。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="1c5a3-111">OpenScopeOnMemory 方法</span><span class="sxs-lookup"><span data-stu-id="1c5a3-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="1c5a3-112">将打开一个包含现有的元数据的内存区域。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="1c5a3-113">也就是说，此方法打开现有数据视为元数据的内存的指定的区域。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c5a3-114">要求</span><span class="sxs-lookup"><span data-stu-id="1c5a3-114">Requirements</span></span>  
 <span data-ttu-id="1c5a3-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c5a3-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c5a3-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1c5a3-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c5a3-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1c5a3-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1c5a3-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="1c5a3-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c5a3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c5a3-119">See also</span></span>

- [<span data-ttu-id="1c5a3-120">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="1c5a3-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="1c5a3-121">元数据接口</span><span class="sxs-lookup"><span data-stu-id="1c5a3-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
