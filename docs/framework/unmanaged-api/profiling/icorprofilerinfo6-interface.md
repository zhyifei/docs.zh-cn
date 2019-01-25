---
title: ICorProfilerInfo6 Interface
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53120508c4810270747f749f1adfbae6ba800404
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567888"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="e1ddf-102">ICorProfilerInfo6 Interface</span><span class="sxs-lookup"><span data-stu-id="e1ddf-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="e1ddf-103">[.NET Framework 4.6 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="e1ddf-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="e1ddf-104">子类[ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)为给定的 NGen 模块和内联给定方法中定义的所有方法提供一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="e1ddf-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1ddf-105">方法</span><span class="sxs-lookup"><span data-stu-id="e1ddf-105">Methods</span></span>  
  
|<span data-ttu-id="e1ddf-106">方法</span><span class="sxs-lookup"><span data-stu-id="e1ddf-106">Method</span></span>|<span data-ttu-id="e1ddf-107">描述</span><span class="sxs-lookup"><span data-stu-id="e1ddf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1ddf-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法</span><span class="sxs-lookup"><span data-stu-id="e1ddf-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="e1ddf-109">返回属于给定的 NGen 模块且是内联给定方法的正文中的所有方法的枚举器。</span><span class="sxs-lookup"><span data-stu-id="e1ddf-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1ddf-110">要求</span><span class="sxs-lookup"><span data-stu-id="e1ddf-110">Requirements</span></span>  
 <span data-ttu-id="e1ddf-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1ddf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ddf-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e1ddf-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e1ddf-113">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ddf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ddf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1ddf-114">See also</span></span>
- [<span data-ttu-id="e1ddf-115">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="e1ddf-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
