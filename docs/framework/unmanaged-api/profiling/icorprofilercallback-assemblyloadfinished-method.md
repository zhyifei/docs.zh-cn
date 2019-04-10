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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198369"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="a4f5b-102">ICorProfilerCallback::AssemblyLoadFinished 方法</span><span class="sxs-lookup"><span data-stu-id="a4f5b-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="a4f5b-103">通知探查器程序集已完成加载。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4f5b-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4f5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4f5b-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="a4f5b-106">[in]标识已加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a4f5b-107">[in]一个 HRESULT，指示是否已完成的程序集加载成功。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4f5b-108">备注</span><span class="sxs-lookup"><span data-stu-id="a4f5b-108">Remarks</span></span>  
 <span data-ttu-id="a4f5b-109">值`assemblyId`不是有效信息请求直到`AssemblyLoadFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="a4f5b-110">加载程序集的某些部分可能会继续后`AssemblyLoadFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="a4f5b-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a4f5b-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功加载程序集的第一部分。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4f5b-113">要求</span><span class="sxs-lookup"><span data-stu-id="a4f5b-113">Requirements</span></span>  
 <span data-ttu-id="a4f5b-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4f5b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4f5b-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a4f5b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a4f5b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4f5b-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4f5b-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a4f5b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4f5b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4f5b-118">See also</span></span>

- [<span data-ttu-id="a4f5b-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a4f5b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
