---
title: "ICorProfilerInfo4::EnumThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.EnumThreads
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 20022a3b7353c0e43aaa44e368c06cd79906956e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="8de01-102">ICorProfilerInfo4::EnumThreads 方法</span><span class="sxs-lookup"><span data-stu-id="8de01-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="8de01-103">返回一个枚举器提供方法以按顺序循环访问集合的所分析进程中的所有托管线程。</span><span class="sxs-lookup"><span data-stu-id="8de01-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de01-104">语法</span><span class="sxs-lookup"><span data-stu-id="8de01-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8de01-105">参数</span><span class="sxs-lookup"><span data-stu-id="8de01-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="8de01-106">[out]指向的指针[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="8de01-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8de01-107">备注</span><span class="sxs-lookup"><span data-stu-id="8de01-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de01-108">要求</span><span class="sxs-lookup"><span data-stu-id="8de01-108">Requirements</span></span>  
 <span data-ttu-id="8de01-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8de01-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de01-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8de01-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8de01-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8de01-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8de01-112">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de01-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de01-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8de01-113">See Also</span></span>  
 [<span data-ttu-id="8de01-114">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="8de01-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="8de01-115">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="8de01-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="8de01-116">分析接口</span><span class="sxs-lookup"><span data-stu-id="8de01-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8de01-117">分析</span><span class="sxs-lookup"><span data-stu-id="8de01-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
