---
title: ICorProfilerInfo7 接口
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a734bfdef89d4f8f9459f49a3ce2cee83faef9f6
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250991"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="833bf-102">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="833bf-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="833bf-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="833bf-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="833bf-104">子类[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) ，它提供了用于将新应用的方法对模块定义元数据使您可以访问的内存中的符号流。</span><span class="sxs-lookup"><span data-stu-id="833bf-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="833bf-105">方法</span><span class="sxs-lookup"><span data-stu-id="833bf-105">Methods</span></span>  
  
|<span data-ttu-id="833bf-106">方法</span><span class="sxs-lookup"><span data-stu-id="833bf-106">Method</span></span>|<span data-ttu-id="833bf-107">描述</span><span class="sxs-lookup"><span data-stu-id="833bf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="833bf-108">ApplyMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="833bf-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="833bf-109">应用新定义的元数据`IMetadataEmit::Define*`方法添加到指定的模块。</span><span class="sxs-lookup"><span data-stu-id="833bf-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="833bf-110">GetInMemorySymbolsLength 方法</span><span class="sxs-lookup"><span data-stu-id="833bf-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="833bf-111">返回内存中的符号流的长度。</span><span class="sxs-lookup"><span data-stu-id="833bf-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="833bf-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="833bf-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="833bf-113">从内存中的符号流读取字节数。</span><span class="sxs-lookup"><span data-stu-id="833bf-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="833bf-114">要求</span><span class="sxs-lookup"><span data-stu-id="833bf-114">Requirements</span></span>  
 <span data-ttu-id="833bf-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="833bf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="833bf-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="833bf-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="833bf-117">**.NET Framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="833bf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="833bf-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="833bf-118">See also</span></span>

- [<span data-ttu-id="833bf-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="833bf-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
