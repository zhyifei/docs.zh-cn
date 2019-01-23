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
ms.openlocfilehash: e92ca55a04032ad9950888eb59e33ee815b14d42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514595"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="f7f23-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="f7f23-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="f7f23-103">时调用`catch`阻止有关内部公共语言运行时 (CLR) 自身执行了异常。</span><span class="sxs-lookup"><span data-stu-id="f7f23-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="f7f23-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="f7f23-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f23-105">语法</span><span class="sxs-lookup"><span data-stu-id="f7f23-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f7f23-106">要求</span><span class="sxs-lookup"><span data-stu-id="f7f23-106">Requirements</span></span>  
 <span data-ttu-id="f7f23-107">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7f23-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f23-108">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7f23-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7f23-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7f23-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7f23-110">**.NET framework 版本：** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="f7f23-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f23-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7f23-111">See also</span></span>
- [<span data-ttu-id="f7f23-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f7f23-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f7f23-113">ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="f7f23-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
