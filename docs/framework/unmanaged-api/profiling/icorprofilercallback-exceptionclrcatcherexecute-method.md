---
title: ICorProfilerCallback::ExceptionCLRCatcherExecute 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b640a6dee9ae50278d6a844d20d21eae156e9dd7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200956"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="cc518-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="cc518-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="cc518-103">时调用`catch`阻止有关内部公共语言运行时 (CLR) 自身执行了异常。</span><span class="sxs-lookup"><span data-stu-id="cc518-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="cc518-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="cc518-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc518-105">语法</span><span class="sxs-lookup"><span data-stu-id="cc518-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cc518-106">要求</span><span class="sxs-lookup"><span data-stu-id="cc518-106">Requirements</span></span>  
 <span data-ttu-id="cc518-107">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc518-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc518-108">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cc518-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cc518-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc518-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc518-110">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="cc518-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc518-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc518-111">See also</span></span>

- [<span data-ttu-id="cc518-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="cc518-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cc518-113">ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="cc518-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
