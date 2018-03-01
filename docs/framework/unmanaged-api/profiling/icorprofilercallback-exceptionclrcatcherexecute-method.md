---
title: "ICorProfilerCallback::ExceptionCLRCatcherExecute 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c5d278fa196836d18b8515bee5af1946b2ca4d74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="f6bb9-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="f6bb9-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="f6bb9-103">时调用`catch`阻止异常在公共语言运行时 (CLR) 自身内执行的。</span><span class="sxs-lookup"><span data-stu-id="f6bb9-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="f6bb9-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="f6bb9-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6bb9-105">语法</span><span class="sxs-lookup"><span data-stu-id="f6bb9-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f6bb9-106">惠?</span><span class="sxs-lookup"><span data-stu-id="f6bb9-106">Requirements</span></span>  
 <span data-ttu-id="f6bb9-107">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6bb9-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6bb9-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6bb9-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6bb9-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6bb9-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6bb9-110">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="f6bb9-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6bb9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6bb9-111">See Also</span></span>  
 [<span data-ttu-id="f6bb9-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f6bb9-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f6bb9-113">ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="f6bb9-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
