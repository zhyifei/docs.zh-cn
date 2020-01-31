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
ms.openlocfilehash: f14dff33217656c35379a214f007ccb3642ef4b1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866450"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="2886d-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="2886d-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="2886d-103">当在公共语言运行时（CLR）本身内执行异常的 `catch` 块时调用。</span><span class="sxs-lookup"><span data-stu-id="2886d-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="2886d-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="2886d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2886d-105">语法</span><span class="sxs-lookup"><span data-stu-id="2886d-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="2886d-106">需求</span><span class="sxs-lookup"><span data-stu-id="2886d-106">Requirements</span></span>  
 <span data-ttu-id="2886d-107">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2886d-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2886d-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2886d-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2886d-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2886d-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2886d-110">**.NET Framework 版本：** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="2886d-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2886d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2886d-111">See also</span></span>

- [<span data-ttu-id="2886d-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2886d-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2886d-113">ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="2886d-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
