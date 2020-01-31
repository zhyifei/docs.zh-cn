---
title: ICorProfilerCallback7 接口
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: e61f6a104b8b9613db32ed6912395fd07c18dcff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864812"
---
# <a name="icorprofilercallback7-interface"></a><span data-ttu-id="1d16f-102">ICorProfilerCallback7 接口</span><span class="sxs-lookup"><span data-stu-id="1d16f-102">ICorProfilerCallback7 Interface</span></span>
<span data-ttu-id="1d16f-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="1d16f-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="1d16f-104">提供回调方法的 [ICorProfilerCallback6](icorprofilercallback6-interface.md) 的子类，公共语言运行时使用该方法通知探查器已更新与内存中模块关联的符号流。</span><span class="sxs-lookup"><span data-stu-id="1d16f-104">A subclass of [ICorProfilerCallback6](icorprofilercallback6-interface.md) that provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1d16f-105">方法</span><span class="sxs-lookup"><span data-stu-id="1d16f-105">Methods</span></span>  
  
|<span data-ttu-id="1d16f-106">方法</span><span class="sxs-lookup"><span data-stu-id="1d16f-106">Method</span></span>|<span data-ttu-id="1d16f-107">描述</span><span class="sxs-lookup"><span data-stu-id="1d16f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1d16f-108">ModuleInMemorySymbolsUpdated 方法</span><span class="sxs-lookup"><span data-stu-id="1d16f-108">ModuleInMemorySymbolsUpdated Method</span></span>](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|<span data-ttu-id="1d16f-109">通知探查器已更新与内存中模块关联的符号流。</span><span class="sxs-lookup"><span data-stu-id="1d16f-109">Notifies the profiler that the symbol stream associated with an in-memory module is updated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d16f-110">需求</span><span class="sxs-lookup"><span data-stu-id="1d16f-110">Requirements</span></span>  
 <span data-ttu-id="1d16f-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d16f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d16f-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d16f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d16f-113">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d16f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d16f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d16f-114">See also</span></span>

- [<span data-ttu-id="1d16f-115">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="1d16f-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
