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
ms.openlocfilehash: 607143d7848534329a55a9caebdb6b9175b2749c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866411"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="464c5-102">ICorProfilerCallback::ExceptionSearchFilterLeave 方法</span><span class="sxs-lookup"><span data-stu-id="464c5-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="464c5-103">通知探查器用户筛选器刚刚执行完毕。</span><span class="sxs-lookup"><span data-stu-id="464c5-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="464c5-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="464c5-105">需求</span><span class="sxs-lookup"><span data-stu-id="464c5-105">Requirements</span></span>  
 <span data-ttu-id="464c5-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="464c5-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="464c5-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="464c5-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="464c5-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="464c5-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="464c5-109">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="464c5-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464c5-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="464c5-110">See also</span></span>

- [<span data-ttu-id="464c5-111">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="464c5-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="464c5-112">ExceptionSearchFilterEnter 方法</span><span class="sxs-lookup"><span data-stu-id="464c5-112">ExceptionSearchFilterEnter Method</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)
