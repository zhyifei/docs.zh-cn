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
ms.workload: dotnet
ms.openlocfilehash: 5f539a93b72c7bf3570dd3cf4cb484564999699c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="d408b-102">ICorProfilerCallback::ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="d408b-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="d408b-103">时调用`catch`阻止阻止公共语言运行时 (CLR) 自身内找到异常。</span><span class="sxs-lookup"><span data-stu-id="d408b-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="d408b-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="d408b-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d408b-105">语法</span><span class="sxs-lookup"><span data-stu-id="d408b-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d408b-106">惠?</span><span class="sxs-lookup"><span data-stu-id="d408b-106">Requirements</span></span>  
 <span data-ttu-id="d408b-107">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d408b-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d408b-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d408b-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d408b-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d408b-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d408b-110">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="d408b-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d408b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d408b-111">See Also</span></span>  
 [<span data-ttu-id="d408b-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d408b-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d408b-113">ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="d408b-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
