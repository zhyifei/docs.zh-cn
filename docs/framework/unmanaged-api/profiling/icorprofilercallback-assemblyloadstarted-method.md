---
title: "ICorProfilerCallback::AssemblyLoadStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyLoadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadStarted method [.NET Framework profiling]
- AssemblyLoadStarted method [.NET Framework profiling]
ms.assetid: 67e8209d-a0ca-4118-a6e6-c1ee0abc2221
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 654cc5fb445184bd07d145701898239bee3e9c8b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyloadstarted-method"></a><span data-ttu-id="29aef-102">ICorProfilerCallback::AssemblyLoadStarted 方法</span><span class="sxs-lookup"><span data-stu-id="29aef-102">ICorProfilerCallback::AssemblyLoadStarted Method</span></span>
<span data-ttu-id="29aef-103">通知探查器正在加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="29aef-103">Notifies the profiler that an assembly is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29aef-104">语法</span><span class="sxs-lookup"><span data-stu-id="29aef-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29aef-105">参数</span><span class="sxs-lookup"><span data-stu-id="29aef-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="29aef-106">[in]标识正在加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="29aef-106">[in] Identifies the assembly that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29aef-107">备注</span><span class="sxs-lookup"><span data-stu-id="29aef-107">Remarks</span></span>  
 <span data-ttu-id="29aef-108">值`assemblyId`无效的信息请求之前，不能[icorprofilercallback:: Assemblyloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="29aef-108">The value of `assemblyId` is not valid for an information request until the [ICorProfilerCallback::AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29aef-109">要求</span><span class="sxs-lookup"><span data-stu-id="29aef-109">Requirements</span></span>  
 <span data-ttu-id="29aef-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="29aef-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29aef-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29aef-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29aef-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29aef-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29aef-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29aef-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29aef-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29aef-114">See Also</span></span>  
 [<span data-ttu-id="29aef-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="29aef-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
