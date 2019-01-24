---
title: ICorProfilerCallback::ExceptionCLRCatcherFound 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: edbd48c910c89c9dd5feea33d9598933fd63befa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729770"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="53dd1-102">ICorProfilerCallback::ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="53dd1-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="53dd1-103">时调用`catch`阻止公共语言运行时 (CLR) 自身内找到异常。</span><span class="sxs-lookup"><span data-stu-id="53dd1-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="53dd1-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="53dd1-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53dd1-105">语法</span><span class="sxs-lookup"><span data-stu-id="53dd1-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="53dd1-106">要求</span><span class="sxs-lookup"><span data-stu-id="53dd1-106">Requirements</span></span>  
 <span data-ttu-id="53dd1-107">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53dd1-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53dd1-108">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53dd1-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53dd1-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53dd1-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53dd1-110">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="53dd1-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53dd1-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="53dd1-111">See also</span></span>
- [<span data-ttu-id="53dd1-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="53dd1-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="53dd1-113">ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="53dd1-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
