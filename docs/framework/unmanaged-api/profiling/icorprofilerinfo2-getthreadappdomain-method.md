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
ms.openlocfilehash: 7c1ee1c39fbf2dcc1f16df3bc94a235676a216dd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862563"
---
# <a name="icorprofilerinfo2getthreadappdomain-method"></a><span data-ttu-id="196e4-102">ICorProfilerInfo2::GetThreadAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="196e4-102">ICorProfilerInfo2::GetThreadAppDomain Method</span></span>
<span data-ttu-id="196e4-103">获取指定线程当前正在执行代码的应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="196e4-103">Gets the ID of the application domain in which the specified thread is currently executing code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="196e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="196e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadAppDomain(  
    [in]  ThreadID threadId,  
    [out] AppDomainID *pAppDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="196e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="196e4-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="196e4-106">中指定线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="196e4-106">[in] The ID specifying the thread.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="196e4-107">弄指向应用程序域的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="196e4-107">[out] A pointer to the ID of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="196e4-108">需求</span><span class="sxs-lookup"><span data-stu-id="196e4-108">Requirements</span></span>  
 <span data-ttu-id="196e4-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="196e4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="196e4-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="196e4-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="196e4-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="196e4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="196e4-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="196e4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="196e4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="196e4-113">See also</span></span>

- [<span data-ttu-id="196e4-114">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="196e4-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="196e4-115">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="196e4-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
