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
ms.openlocfilehash: 165981627337c562dd3721b7d93cb2027d0a0c37
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444940"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="a7647-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="a7647-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="a7647-103">当在公共语言运行时（CLR）本身内执行异常的 `catch` 块时调用。</span><span class="sxs-lookup"><span data-stu-id="a7647-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="a7647-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="a7647-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7647-105">语法</span><span class="sxs-lookup"><span data-stu-id="a7647-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a7647-106">要求</span><span class="sxs-lookup"><span data-stu-id="a7647-106">Requirements</span></span>  
 <span data-ttu-id="a7647-107">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7647-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7647-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7647-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7647-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7647-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7647-110">**.NET Framework 版本：** 1.1、1。0</span><span class="sxs-lookup"><span data-stu-id="a7647-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7647-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7647-111">See also</span></span>

- [<span data-ttu-id="a7647-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a7647-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a7647-113">ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="a7647-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
