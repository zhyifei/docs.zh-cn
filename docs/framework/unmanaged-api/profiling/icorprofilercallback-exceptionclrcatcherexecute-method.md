---
title: "ICorProfilerCallback::ExceptionCLRCatcherExecute 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b63f428cd75ed98d30e4b6ecca69dbe3b5b5656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="c6bcb-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="c6bcb-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="c6bcb-103">时调用`catch`阻止异常在公共语言运行时 (CLR) 自身内执行的。</span><span class="sxs-lookup"><span data-stu-id="c6bcb-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="c6bcb-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="c6bcb-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6bcb-105">语法</span><span class="sxs-lookup"><span data-stu-id="c6bcb-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c6bcb-106">要求</span><span class="sxs-lookup"><span data-stu-id="c6bcb-106">Requirements</span></span>  
 <span data-ttu-id="c6bcb-107">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6bcb-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6bcb-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6bcb-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6bcb-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6bcb-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6bcb-110">**.NET framework 版本：** 1.1、 1.0</span><span class="sxs-lookup"><span data-stu-id="c6bcb-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6bcb-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6bcb-111">See Also</span></span>  
 [<span data-ttu-id="c6bcb-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c6bcb-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c6bcb-113">ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="c6bcb-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
