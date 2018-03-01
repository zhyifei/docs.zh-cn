---
title: "ICorProfilerInfo2::GetThreadAppDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c6e596a4610052d7586978a4e770d5df60b38ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="2c511-102">ICorProfilerInfo2::GetThreadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="2c511-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="2c511-103">获取在其中指定的线程当前正在执行代码的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="2c511-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c511-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c511-104">Syntax</span></span>  
  
```  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c511-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c511-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="2c511-106">[in]指定线程 ID。</span><span class="sxs-lookup"><span data-stu-id="2c511-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="2c511-107">[out]指向应用程序域的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="2c511-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c511-108">惠?</span><span class="sxs-lookup"><span data-stu-id="2c511-108">Requirements</span></span>  
 <span data-ttu-id="2c511-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c511-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c511-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c511-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c511-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c511-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c511-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c511-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c511-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c511-113">See Also</span></span>  
 [<span data-ttu-id="2c511-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="2c511-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2c511-115">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="2c511-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
