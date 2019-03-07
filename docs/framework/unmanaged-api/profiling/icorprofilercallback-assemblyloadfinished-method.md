---
title: ICorProfilerCallback::AssemblyLoadFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bb5586271c252879b503dd093c88380197d5bce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479722"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="792dc-102">ICorProfilerCallback::AssemblyLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="792dc-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="792dc-103">通知探查器程序集已完成加载。</span><span class="sxs-lookup"><span data-stu-id="792dc-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="792dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="792dc-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="792dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="792dc-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="792dc-106">[in]标识已加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="792dc-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="792dc-107">[in]一个 HRESULT，指示是否已完成的程序集加载成功。</span><span class="sxs-lookup"><span data-stu-id="792dc-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="792dc-108">备注</span><span class="sxs-lookup"><span data-stu-id="792dc-108">Remarks</span></span>  
 <span data-ttu-id="792dc-109">值`assemblyId`不是有效信息请求直到`AssemblyLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="792dc-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="792dc-110">加载程序集的某些部分可能会继续后`AssemblyLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="792dc-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="792dc-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="792dc-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="792dc-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功加载程序集的第一部分。</span><span class="sxs-lookup"><span data-stu-id="792dc-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="792dc-113">要求</span><span class="sxs-lookup"><span data-stu-id="792dc-113">Requirements</span></span>  
 <span data-ttu-id="792dc-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="792dc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="792dc-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="792dc-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="792dc-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="792dc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="792dc-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="792dc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="792dc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="792dc-118">See also</span></span>
- [<span data-ttu-id="792dc-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="792dc-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
