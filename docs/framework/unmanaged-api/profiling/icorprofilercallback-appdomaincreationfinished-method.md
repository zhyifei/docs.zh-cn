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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35dac5fd000f5ae30af917e3813239b2e365e64a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153980"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="f10c6-102">ICorProfilerCallback::AppDomainCreationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="f10c6-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="f10c6-103">通知探查器已创建的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f10c6-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="f10c6-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="f10c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="f10c6-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="f10c6-106">[in]标识已创建的域。</span><span class="sxs-lookup"><span data-stu-id="f10c6-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="f10c6-107">[in]一个 HRESULT，指示是否已成功完成创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="f10c6-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f10c6-108">备注</span><span class="sxs-lookup"><span data-stu-id="f10c6-108">Remarks</span></span>  
 <span data-ttu-id="f10c6-109">应用程序 ID 不是有效的任何信息请求直到`AppDomainCreationFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="f10c6-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="f10c6-110">加载应用程序域的某些部分可能会继续后`AppDomainCreationFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="f10c6-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="f10c6-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="f10c6-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="f10c6-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功创建应用程序域的第一部分。</span><span class="sxs-lookup"><span data-stu-id="f10c6-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f10c6-113">要求</span><span class="sxs-lookup"><span data-stu-id="f10c6-113">Requirements</span></span>  
 <span data-ttu-id="f10c6-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f10c6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f10c6-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f10c6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f10c6-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f10c6-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f10c6-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f10c6-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f10c6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f10c6-118">See also</span></span>

- [<span data-ttu-id="f10c6-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="f10c6-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
