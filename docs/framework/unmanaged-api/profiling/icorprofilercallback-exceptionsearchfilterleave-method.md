---
title: ICorProfilerCallback::ExceptionSearchFilterLeave 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fcbd225acd3f4f24311d08b04c971e2550b8ef5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533567"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="a8fce-102">ICorProfilerCallback::ExceptionSearchFilterLeave 方法</span><span class="sxs-lookup"><span data-stu-id="a8fce-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="a8fce-103">通知探查器的用户筛选器只需执行完毕。</span><span class="sxs-lookup"><span data-stu-id="a8fce-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8fce-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8fce-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a8fce-105">要求</span><span class="sxs-lookup"><span data-stu-id="a8fce-105">Requirements</span></span>  
 <span data-ttu-id="a8fce-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8fce-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8fce-107">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8fce-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8fce-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8fce-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8fce-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8fce-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8fce-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8fce-110">See also</span></span>
- [<span data-ttu-id="a8fce-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a8fce-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a8fce-112">ExceptionSearchFilterEnter 方法</span><span class="sxs-lookup"><span data-stu-id="a8fce-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
