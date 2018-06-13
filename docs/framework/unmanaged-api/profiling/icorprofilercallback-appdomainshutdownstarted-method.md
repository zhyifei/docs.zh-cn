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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd1e5daada8793e94980afc5f0cf509915bd288e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450923"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="6409d-102">ICorProfilerCallback::AppDomainShutdownStarted 方法</span><span class="sxs-lookup"><span data-stu-id="6409d-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="6409d-103">通知探查器正在从进程卸载程序的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="6409d-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6409d-104">语法</span><span class="sxs-lookup"><span data-stu-id="6409d-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6409d-105">参数</span><span class="sxs-lookup"><span data-stu-id="6409d-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="6409d-106">[in]标识应用程序的程序集存储在其中的域。</span><span class="sxs-lookup"><span data-stu-id="6409d-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6409d-107">备注</span><span class="sxs-lookup"><span data-stu-id="6409d-107">Remarks</span></span>  
 <span data-ttu-id="6409d-108">值`appDomainId`无效之后的所有信息请求，不能`AppDomainShutdownStarted`方法返回-这是探查器的最后一次机会获取有关此应用程序域的信息。</span><span class="sxs-lookup"><span data-stu-id="6409d-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6409d-109">要求</span><span class="sxs-lookup"><span data-stu-id="6409d-109">Requirements</span></span>  
 <span data-ttu-id="6409d-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6409d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6409d-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6409d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6409d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6409d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6409d-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6409d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6409d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6409d-114">See Also</span></span>  
 [<span data-ttu-id="6409d-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6409d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
