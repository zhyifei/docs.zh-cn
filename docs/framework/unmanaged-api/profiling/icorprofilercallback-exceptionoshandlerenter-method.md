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
ms.openlocfilehash: 7842e7a8f12a58aa56fd5be5674b183fc515f51b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608438"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="ff360-102">ICorProfilerCallback::ExceptionOSHandlerEnter 方法</span><span class="sxs-lookup"><span data-stu-id="ff360-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="ff360-103">未实现。</span><span class="sxs-lookup"><span data-stu-id="ff360-103">Not implemented.</span></span> <span data-ttu-id="ff360-104">需要非托管的异常信息的探查器必须获取此信息通过其他方式。</span><span class="sxs-lookup"><span data-stu-id="ff360-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff360-105">语法</span><span class="sxs-lookup"><span data-stu-id="ff360-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ff360-106">要求</span><span class="sxs-lookup"><span data-stu-id="ff360-106">Requirements</span></span>  
 <span data-ttu-id="ff360-107">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ff360-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff360-108">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff360-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff360-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff360-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff360-110">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff360-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff360-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff360-111">See also</span></span>
- [<span data-ttu-id="ff360-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="ff360-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
