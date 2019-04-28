---
title: ICorProfilerCallback::AssemblyLoadStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a96a2a0d6e4bc48a46850aeaadd17c2669419cef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597447"
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="10799-102">ICorProfilerCallback::AssemblyLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="10799-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="10799-103">通知探查器正在加载程序集。</span><span class="sxs-lookup"><span data-stu-id="10799-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10799-104">语法</span><span class="sxs-lookup"><span data-stu-id="10799-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10799-105">参数</span><span class="sxs-lookup"><span data-stu-id="10799-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="10799-106">[in]标识要加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="10799-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10799-107">备注</span><span class="sxs-lookup"><span data-stu-id="10799-107">Remarks</span></span>  
 <span data-ttu-id="10799-108">值`assemblyId`不是有效的信息请求之前[icorprofilercallback:: Assemblyloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="10799-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10799-109">要求</span><span class="sxs-lookup"><span data-stu-id="10799-109">Requirements</span></span>  
 <span data-ttu-id="10799-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10799-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10799-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="10799-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="10799-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10799-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10799-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10799-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10799-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="10799-114">See also</span></span>

- [<span data-ttu-id="10799-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="10799-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
