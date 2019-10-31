---
title: ICorProfilerInfo7 接口
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4c7e94ffa60bcfaead009e1a8baa9b54b2e8ab7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125058"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="467d0-102">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="467d0-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="467d0-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="467d0-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="467d0-104">[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)的子类，它提供了一种方法，用于将新定义的元数据应用于模块，并提供对内存中符号流的访问。</span><span class="sxs-lookup"><span data-stu-id="467d0-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="467d0-105">方法</span><span class="sxs-lookup"><span data-stu-id="467d0-105">Methods</span></span>  
  
|<span data-ttu-id="467d0-106">方法</span><span class="sxs-lookup"><span data-stu-id="467d0-106">Method</span></span>|<span data-ttu-id="467d0-107">描述</span><span class="sxs-lookup"><span data-stu-id="467d0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="467d0-108">ApplyMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="467d0-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="467d0-109">将 `IMetadataEmit::Define*` 方法新定义的元数据应用于指定的模块。</span><span class="sxs-lookup"><span data-stu-id="467d0-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="467d0-110">GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="467d0-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="467d0-111">返回内存中符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="467d0-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="467d0-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="467d0-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="467d0-113">从内存中的符号流中读取字节。</span><span class="sxs-lookup"><span data-stu-id="467d0-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="467d0-114">要求</span><span class="sxs-lookup"><span data-stu-id="467d0-114">Requirements</span></span>  
 <span data-ttu-id="467d0-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="467d0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="467d0-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="467d0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="467d0-117">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="467d0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467d0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="467d0-118">See also</span></span>

- [<span data-ttu-id="467d0-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="467d0-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
