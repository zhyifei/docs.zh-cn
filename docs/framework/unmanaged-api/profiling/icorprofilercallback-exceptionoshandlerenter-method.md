---
title: ICorProfilerCallback::ExceptionOSHandlerEnter 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: b3088308e75fb7cbffcc439ab4440255ed0fb2b9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444910"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="26c8c-102">ICorProfilerCallback::ExceptionOSHandlerEnter 方法</span><span class="sxs-lookup"><span data-stu-id="26c8c-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="26c8c-103">未实现。</span><span class="sxs-lookup"><span data-stu-id="26c8c-103">Not implemented.</span></span> <span data-ttu-id="26c8c-104">需要非托管异常信息的探查器必须通过其他方式获取此信息。</span><span class="sxs-lookup"><span data-stu-id="26c8c-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c8c-105">语法</span><span class="sxs-lookup"><span data-stu-id="26c8c-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="26c8c-106">要求</span><span class="sxs-lookup"><span data-stu-id="26c8c-106">Requirements</span></span>  
 <span data-ttu-id="26c8c-107">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26c8c-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26c8c-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26c8c-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="26c8c-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26c8c-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26c8c-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26c8c-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c8c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26c8c-111">See also</span></span>

- [<span data-ttu-id="26c8c-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="26c8c-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
