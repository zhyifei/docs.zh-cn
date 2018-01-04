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
ms.workload: dotnet
ms.openlocfilehash: 13282bec74df5e6159148aa4fbe92a84d035e044
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="deb68-102">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="deb68-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="deb68-103">[支持版本：[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 及更高版本]</span><span class="sxs-lookup"><span data-stu-id="deb68-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="deb68-104">一个子类[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) ，它提供了新应用的方法定义模块的元数据使您可以访问的内存中的符号流。</span><span class="sxs-lookup"><span data-stu-id="deb68-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="deb68-105">方法</span><span class="sxs-lookup"><span data-stu-id="deb68-105">Methods</span></span>  
  
|<span data-ttu-id="deb68-106">方法</span><span class="sxs-lookup"><span data-stu-id="deb68-106">Method</span></span>|<span data-ttu-id="deb68-107">描述</span><span class="sxs-lookup"><span data-stu-id="deb68-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="deb68-108">ApplyMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="deb68-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="deb68-109">将应用新定义的元数据`IMetadataEmit::Define*`到指定的模块的方法。</span><span class="sxs-lookup"><span data-stu-id="deb68-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="deb68-110">GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="deb68-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="deb68-111">返回的内存中的符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="deb68-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="deb68-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="deb68-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="deb68-113">从内存中的符号流读取字节。</span><span class="sxs-lookup"><span data-stu-id="deb68-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="deb68-114">惠?</span><span class="sxs-lookup"><span data-stu-id="deb68-114">Requirements</span></span>  
 <span data-ttu-id="deb68-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="deb68-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deb68-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="deb68-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="deb68-117">**.NET framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deb68-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb68-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="deb68-118">See Also</span></span>  
 [<span data-ttu-id="deb68-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="deb68-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
