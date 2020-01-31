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
ms.openlocfilehash: a543e5119a3ad5580fb67c31dc0e59ab62eab571
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866487"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="a8f32-102">ICorProfilerCallback::ExceptionCLRCatcherFound 方法</span><span class="sxs-lookup"><span data-stu-id="a8f32-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="a8f32-103">当在公共语言运行时（CLR）本身内找到异常的 `catch` 块时调用。</span><span class="sxs-lookup"><span data-stu-id="a8f32-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="a8f32-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="a8f32-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8f32-105">语法</span><span class="sxs-lookup"><span data-stu-id="a8f32-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a8f32-106">需求</span><span class="sxs-lookup"><span data-stu-id="a8f32-106">Requirements</span></span>  
 <span data-ttu-id="a8f32-107">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f32-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8f32-108">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8f32-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8f32-109">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8f32-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8f32-110">**.NET Framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="a8f32-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f32-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8f32-111">See also</span></span>

- [<span data-ttu-id="a8f32-112">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a8f32-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a8f32-113">ExceptionCLRCatcherExecute 方法</span><span class="sxs-lookup"><span data-stu-id="a8f32-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
