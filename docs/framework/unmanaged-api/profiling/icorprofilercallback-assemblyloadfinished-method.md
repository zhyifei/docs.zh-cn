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
ms.openlocfilehash: e32af790c755f65b5435455c326d011656da19ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198369"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="f23b9-102">ICorProfilerCallback::AssemblyLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="f23b9-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="f23b9-103">通知探查器程序集已完成加载。</span><span class="sxs-lookup"><span data-stu-id="f23b9-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f23b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="f23b9-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f23b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="f23b9-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="f23b9-106">[in]标识已加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="f23b9-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="f23b9-107">[in]一个 HRESULT，指示是否已完成的程序集加载成功。</span><span class="sxs-lookup"><span data-stu-id="f23b9-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f23b9-108">备注</span><span class="sxs-lookup"><span data-stu-id="f23b9-108">Remarks</span></span>  
 <span data-ttu-id="f23b9-109">值`assemblyId`不是有效信息请求直到`AssemblyLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="f23b9-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="f23b9-110">加载程序集的某些部分可能会继续后`AssemblyLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="f23b9-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="f23b9-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="f23b9-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="f23b9-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功加载程序集的第一部分。</span><span class="sxs-lookup"><span data-stu-id="f23b9-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f23b9-113">要求</span><span class="sxs-lookup"><span data-stu-id="f23b9-113">Requirements</span></span>  
 <span data-ttu-id="f23b9-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f23b9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f23b9-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f23b9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f23b9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f23b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f23b9-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f23b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23b9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f23b9-118">See also</span></span>

- [<span data-ttu-id="f23b9-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f23b9-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
