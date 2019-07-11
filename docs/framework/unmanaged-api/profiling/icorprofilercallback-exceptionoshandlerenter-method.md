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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9167b35556fafb33e61e1dc050488aec2b7fa01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776014"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="99b2f-102">ICorProfilerCallback::ExceptionOSHandlerEnter 方法</span><span class="sxs-lookup"><span data-stu-id="99b2f-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="99b2f-103">未实现。</span><span class="sxs-lookup"><span data-stu-id="99b2f-103">Not implemented.</span></span> <span data-ttu-id="99b2f-104">需要非托管的异常信息的探查器必须获取此信息通过其他方式。</span><span class="sxs-lookup"><span data-stu-id="99b2f-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99b2f-105">语法</span><span class="sxs-lookup"><span data-stu-id="99b2f-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="99b2f-106">要求</span><span class="sxs-lookup"><span data-stu-id="99b2f-106">Requirements</span></span>  
 <span data-ttu-id="99b2f-107">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99b2f-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99b2f-108">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="99b2f-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="99b2f-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99b2f-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99b2f-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99b2f-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b2f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="99b2f-111">See also</span></span>

- [<span data-ttu-id="99b2f-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="99b2f-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
