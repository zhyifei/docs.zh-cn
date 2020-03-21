---
title: ICorProfilerCallback::AppDomainCreationFinished 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177067"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="e699a-102">ICorProfilerCallback::AppDomainCreationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="e699a-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="e699a-103">通知探查器已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e699a-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e699a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e699a-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="e699a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="e699a-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="e699a-106">\[in] 标识已创建的域。</span><span class="sxs-lookup"><span data-stu-id="e699a-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="e699a-107">\[in] 指示应用程序域的创建是否成功完成的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="e699a-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="e699a-108">备注</span><span class="sxs-lookup"><span data-stu-id="e699a-108">Remarks</span></span>  
 <span data-ttu-id="e699a-109">在调用方法之前，`AppDomainCreationFinished`应用程序 ID 对任何信息请求无效。</span><span class="sxs-lookup"><span data-stu-id="e699a-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="e699a-110">回调后`AppDomainCreationFinished`加载应用程序域的某些部分可能会继续。</span><span class="sxs-lookup"><span data-stu-id="e699a-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="e699a-111">故障 HRESULT `hrStatus` in 表示失败。</span><span class="sxs-lookup"><span data-stu-id="e699a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e699a-112">但是，HRESULT 的成功仅`hrStatus`表示创建应用程序域的第一部分已成功。</span><span class="sxs-lookup"><span data-stu-id="e699a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e699a-113">要求</span><span class="sxs-lookup"><span data-stu-id="e699a-113">Requirements</span></span>  
 <span data-ttu-id="e699a-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e699a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e699a-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e699a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e699a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e699a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e699a-117">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e699a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e699a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e699a-118">See also</span></span>

- [<span data-ttu-id="e699a-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="e699a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
