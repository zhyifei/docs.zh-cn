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
ms.openlocfilehash: da1aab48e2eef229bb31e9443a5549c3f9fbc621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455297"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="27fa7-102">ICorProfilerInfo6 接口</span><span class="sxs-lookup"><span data-stu-id="27fa7-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="27fa7-103">[在.NET Framework 4.6 和更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="27fa7-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="27fa7-104">一个子类[ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) ，对于给定的 NGen 模块和内联给定方法中定义的所有方法提供的枚举器。</span><span class="sxs-lookup"><span data-stu-id="27fa7-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27fa7-105">方法</span><span class="sxs-lookup"><span data-stu-id="27fa7-105">Methods</span></span>  
  
|<span data-ttu-id="27fa7-106">方法</span><span class="sxs-lookup"><span data-stu-id="27fa7-106">Method</span></span>|<span data-ttu-id="27fa7-107">描述</span><span class="sxs-lookup"><span data-stu-id="27fa7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27fa7-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法</span><span class="sxs-lookup"><span data-stu-id="27fa7-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="27fa7-109">返回属于给定 NGen 模块以及在给定方法的正文中内联的所有方法的枚举数。</span><span class="sxs-lookup"><span data-stu-id="27fa7-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27fa7-110">要求</span><span class="sxs-lookup"><span data-stu-id="27fa7-110">Requirements</span></span>  
 <span data-ttu-id="27fa7-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27fa7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27fa7-112">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27fa7-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27fa7-113">**.NET framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27fa7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27fa7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="27fa7-114">See Also</span></span>  
 [<span data-ttu-id="27fa7-115">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="27fa7-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
