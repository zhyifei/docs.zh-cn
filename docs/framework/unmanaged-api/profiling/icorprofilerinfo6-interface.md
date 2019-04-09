---
title: ICorProfilerInfo6 接口
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
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128929"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="ad987-102">ICorProfilerInfo6 接口</span><span class="sxs-lookup"><span data-stu-id="ad987-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="ad987-103">[.NET Framework 4.6 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="ad987-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="ad987-104">子类[ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)为给定的 NGen 模块和内联给定方法中定义的所有方法提供一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="ad987-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad987-105">方法</span><span class="sxs-lookup"><span data-stu-id="ad987-105">Methods</span></span>  
  
|<span data-ttu-id="ad987-106">方法</span><span class="sxs-lookup"><span data-stu-id="ad987-106">Method</span></span>|<span data-ttu-id="ad987-107">描述</span><span class="sxs-lookup"><span data-stu-id="ad987-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad987-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法</span><span class="sxs-lookup"><span data-stu-id="ad987-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="ad987-109">返回属于给定的 NGen 模块且是内联给定方法的正文中的所有方法的枚举器。</span><span class="sxs-lookup"><span data-stu-id="ad987-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad987-110">要求</span><span class="sxs-lookup"><span data-stu-id="ad987-110">Requirements</span></span>  
 <span data-ttu-id="ad987-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad987-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad987-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad987-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="ad987-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="ad987-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad987-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad987-114">See also</span></span>

- [<span data-ttu-id="ad987-115">分析接口</span><span class="sxs-lookup"><span data-stu-id="ad987-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
