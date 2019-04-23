---
title: ICorProfilerInfo2::GetThreadAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadAppDomain
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadAppDomain
helpviewer_keywords:
- ICorProfilerInfo2::GetThreadAppDomain method [.NET Framework profiling]
- GetThreadAppDomain method [.NET Framework profiling]
ms.assetid: 4a11b264-8540-4732-aa35-bc2d95b95b8e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32a69f948b936dd80ab364583dc2928778b34ba0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174403"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="87431-102">ICorProfilerInfo2::GetThreadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="87431-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="87431-103">获取在其中指定的线程当前正在执行代码的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="87431-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87431-104">语法</span><span class="sxs-lookup"><span data-stu-id="87431-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87431-105">参数</span><span class="sxs-lookup"><span data-stu-id="87431-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="87431-106">[in]指定在线程 ID。</span><span class="sxs-lookup"><span data-stu-id="87431-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="87431-107">[out]指向应用程序域的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="87431-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87431-108">要求</span><span class="sxs-lookup"><span data-stu-id="87431-108">Requirements</span></span>  
 <span data-ttu-id="87431-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87431-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87431-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="87431-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="87431-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87431-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87431-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87431-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87431-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="87431-113">See also</span></span>

- [<span data-ttu-id="87431-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="87431-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="87431-115">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="87431-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
