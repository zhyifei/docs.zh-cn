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
ms.openlocfilehash: a08a0ed8303804df1889973fe3ffab6db93249d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481438"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="1ce58-102">ICorProfilerCallback::AppDomainCreationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="1ce58-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="1ce58-103">通知探查器已创建的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1ce58-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce58-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ce58-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce58-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ce58-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="1ce58-106">[in]标识已创建的域。</span><span class="sxs-lookup"><span data-stu-id="1ce58-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="1ce58-107">[in]一个 HRESULT，指示是否已成功完成创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="1ce58-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ce58-108">备注</span><span class="sxs-lookup"><span data-stu-id="1ce58-108">Remarks</span></span>  
 <span data-ttu-id="1ce58-109">应用程序 ID 不是有效的任何信息请求直到`AppDomainCreationFinished`调用方法。</span><span class="sxs-lookup"><span data-stu-id="1ce58-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="1ce58-110">加载应用程序域的某些部分可能会继续后`AppDomainCreationFinished`回调。</span><span class="sxs-lookup"><span data-stu-id="1ce58-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="1ce58-111">失败的 HRESULT 在`hrStatus`表明发生了故障。</span><span class="sxs-lookup"><span data-stu-id="1ce58-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="1ce58-112">但是，成功的 HRESULT 在`hrStatus`仅表示已成功创建应用程序域的第一部分。</span><span class="sxs-lookup"><span data-stu-id="1ce58-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ce58-113">要求</span><span class="sxs-lookup"><span data-stu-id="1ce58-113">Requirements</span></span>  
 <span data-ttu-id="1ce58-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ce58-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ce58-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ce58-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ce58-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ce58-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ce58-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ce58-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce58-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ce58-118">See also</span></span>
- [<span data-ttu-id="1ce58-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="1ce58-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
