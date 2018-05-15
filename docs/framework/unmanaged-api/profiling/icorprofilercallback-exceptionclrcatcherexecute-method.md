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
ms.openlocfilehash: 6057593362e75044a9b2db32ad5dafe439a551d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="02c6e-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="02c6e-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="02c6e-103">时调用`catch`阻止异常在公共语言运行时 (CLR) 自身内执行的。</span><span class="sxs-lookup"><span data-stu-id="02c6e-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="02c6e-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="02c6e-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02c6e-105">语法</span><span class="sxs-lookup"><span data-stu-id="02c6e-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="02c6e-106">要求</span><span class="sxs-lookup"><span data-stu-id="02c6e-106">Requirements</span></span>  
 <span data-ttu-id="02c6e-107">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02c6e-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c6e-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02c6e-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02c6e-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02c6e-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02c6e-110">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="02c6e-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c6e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="02c6e-111">See Also</span></span>  
 [<span data-ttu-id="02c6e-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="02c6e-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="02c6e-113">ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="02c6e-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
