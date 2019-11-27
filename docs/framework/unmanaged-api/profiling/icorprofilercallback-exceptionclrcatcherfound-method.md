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
ms.openlocfilehash: ef5122d49c428af4faa27f3827a5c60721ef0f74
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435827"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="3051d-102">ICorProfilerCallback::ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="3051d-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="3051d-103">当在公共语言运行时（CLR）本身内找到异常的 `catch` 块时调用。</span><span class="sxs-lookup"><span data-stu-id="3051d-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="3051d-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="3051d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3051d-105">语法</span><span class="sxs-lookup"><span data-stu-id="3051d-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="3051d-106">要求</span><span class="sxs-lookup"><span data-stu-id="3051d-106">Requirements</span></span>  
 <span data-ttu-id="3051d-107">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3051d-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3051d-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3051d-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3051d-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3051d-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3051d-110">**.NET Framework 版本：** 1。0</span><span class="sxs-lookup"><span data-stu-id="3051d-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3051d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3051d-111">See also</span></span>

- [<span data-ttu-id="3051d-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="3051d-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3051d-113">ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="3051d-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
