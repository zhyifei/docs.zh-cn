---
title: "ICorProfilerCallback::ExceptionCLRCatcherFound 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCLRCatcherFound
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ebb1779ca9f09089a071673f92810ea7a9e76b3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="eb02f-102">ICorProfilerCallback::ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="eb02f-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="eb02f-103">时调用`catch`阻止阻止公共语言运行时 (CLR) 自身内找到异常。</span><span class="sxs-lookup"><span data-stu-id="eb02f-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="eb02f-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="eb02f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb02f-105">语法</span><span class="sxs-lookup"><span data-stu-id="eb02f-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="eb02f-106">要求</span><span class="sxs-lookup"><span data-stu-id="eb02f-106">Requirements</span></span>  
 <span data-ttu-id="eb02f-107">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb02f-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb02f-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb02f-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb02f-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb02f-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb02f-110">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="eb02f-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb02f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb02f-111">See Also</span></span>  
 [<span data-ttu-id="eb02f-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="eb02f-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="eb02f-113">ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="eb02f-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
