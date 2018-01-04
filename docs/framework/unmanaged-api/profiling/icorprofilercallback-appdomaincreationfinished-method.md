---
title: "ICorProfilerCallback::AppDomainCreationFinished 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f779e5a7b0b38558593e84c26b33784383765ca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="de85a-102">ICorProfilerCallback::AppDomainCreationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="de85a-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="de85a-103">通知探查器已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="de85a-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de85a-104">语法</span><span class="sxs-lookup"><span data-stu-id="de85a-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="de85a-105">参数</span><span class="sxs-lookup"><span data-stu-id="de85a-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="de85a-106">[in]标识已创建的域。</span><span class="sxs-lookup"><span data-stu-id="de85a-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="de85a-107">[in]指示是否已成功完成创建应用程序域的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="de85a-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de85a-108">备注</span><span class="sxs-lookup"><span data-stu-id="de85a-108">Remarks</span></span>  
 <span data-ttu-id="de85a-109">应用程序 ID 不是有效的任何信息请求到`AppDomainCreationFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="de85a-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="de85a-110">加载的应用程序域的某些部分可能会继续之后`AppDomainCreationFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="de85a-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="de85a-111">失败的 HRESULT 在`hrStatus`指示失败。</span><span class="sxs-lookup"><span data-stu-id="de85a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="de85a-112">但是，HRESULT 为成功，在`hrStatus`仅指示已成功创建应用程序域的第一部分。</span><span class="sxs-lookup"><span data-stu-id="de85a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de85a-113">惠?</span><span class="sxs-lookup"><span data-stu-id="de85a-113">Requirements</span></span>  
 <span data-ttu-id="de85a-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de85a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de85a-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de85a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="de85a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de85a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de85a-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de85a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de85a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="de85a-118">See Also</span></span>  
 [<span data-ttu-id="de85a-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="de85a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
