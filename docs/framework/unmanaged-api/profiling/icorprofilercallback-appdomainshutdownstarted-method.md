---
title: ICorProfilerCallback::AppDomainShutdownStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: 6bbb41f8fd3ac37f1c21fe8b4f6159e3d303777c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445191"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="761b5-102">ICorProfilerCallback::AppDomainShutdownStarted 方法</span><span class="sxs-lookup"><span data-stu-id="761b5-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="761b5-103">通知探查器正在从进程中卸载应用程序域。</span><span class="sxs-lookup"><span data-stu-id="761b5-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="761b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="761b5-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="761b5-105">参数</span><span class="sxs-lookup"><span data-stu-id="761b5-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="761b5-106">中标识要在其中存储应用程序的程序集的域。</span><span class="sxs-lookup"><span data-stu-id="761b5-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="761b5-107">备注</span><span class="sxs-lookup"><span data-stu-id="761b5-107">Remarks</span></span>  
 <span data-ttu-id="761b5-108">`appDomainId` 的值对于 `AppDomainShutdownStarted` 方法返回后的任何信息请求都无效-这是探查器获取有关此应用程序域的信息的最后机会。</span><span class="sxs-lookup"><span data-stu-id="761b5-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="761b5-109">要求</span><span class="sxs-lookup"><span data-stu-id="761b5-109">Requirements</span></span>  
 <span data-ttu-id="761b5-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="761b5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="761b5-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="761b5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="761b5-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="761b5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="761b5-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="761b5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="761b5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="761b5-114">See also</span></span>

- [<span data-ttu-id="761b5-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="761b5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
