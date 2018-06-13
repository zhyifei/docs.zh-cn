---
title: ICorProfilerCallback::ExceptionOSHandlerLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53c71914d8938067ceb5d580d42ffe7d7d8dc1df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450660"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="7c0c2-102">ICorProfilerCallback::ExceptionOSHandlerLeave 方法</span><span class="sxs-lookup"><span data-stu-id="7c0c2-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="7c0c2-103">未实现。</span><span class="sxs-lookup"><span data-stu-id="7c0c2-103">Not implemented.</span></span> <span data-ttu-id="7c0c2-104">需要非托管的异常信息的探查器必须获取此信息通过其他方式。</span><span class="sxs-lookup"><span data-stu-id="7c0c2-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0c2-105">语法</span><span class="sxs-lookup"><span data-stu-id="7c0c2-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7c0c2-106">要求</span><span class="sxs-lookup"><span data-stu-id="7c0c2-106">Requirements</span></span>  
 <span data-ttu-id="7c0c2-107">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c0c2-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0c2-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c0c2-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c0c2-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c0c2-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c0c2-110">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0c2-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0c2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c0c2-111">See Also</span></span>  
 [<span data-ttu-id="7c0c2-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="7c0c2-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
