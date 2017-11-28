---
title: "ICorProfilerInfo7 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a85bf82a01f431e42a5714eeb54e17a34314534
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="39e66-102">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="39e66-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="39e66-103">[支持版本：[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 及更高版本]</span><span class="sxs-lookup"><span data-stu-id="39e66-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="39e66-104">一个子类[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) ，它提供了新应用的方法定义模块的元数据使您可以访问的内存中的符号流。</span><span class="sxs-lookup"><span data-stu-id="39e66-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39e66-105">方法</span><span class="sxs-lookup"><span data-stu-id="39e66-105">Methods</span></span>  
  
|<span data-ttu-id="39e66-106">方法</span><span class="sxs-lookup"><span data-stu-id="39e66-106">Method</span></span>|<span data-ttu-id="39e66-107">描述</span><span class="sxs-lookup"><span data-stu-id="39e66-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39e66-108">ApplyMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="39e66-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="39e66-109">将应用新定义的元数据`IMetadataEmit::Define*`到指定的模块的方法。</span><span class="sxs-lookup"><span data-stu-id="39e66-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="39e66-110">GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="39e66-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="39e66-111">返回的内存中的符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="39e66-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="39e66-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="39e66-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="39e66-113">从内存中的符号流读取字节。</span><span class="sxs-lookup"><span data-stu-id="39e66-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39e66-114">要求</span><span class="sxs-lookup"><span data-stu-id="39e66-114">Requirements</span></span>  
 <span data-ttu-id="39e66-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39e66-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39e66-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39e66-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39e66-117">**.NET framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39e66-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e66-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39e66-118">See Also</span></span>  
 [<span data-ttu-id="39e66-119">分析接口</span><span class="sxs-lookup"><span data-stu-id="39e66-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
