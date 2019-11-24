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
ms.openlocfilehash: eaf0ae2a1b86234495c1804cff8b74331b3e8021
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445271"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="c99c7-102">ICorProfilerCallback::AppDomainCreationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="c99c7-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="c99c7-103">Notifies the profiler that an application domain has been created.</span><span class="sxs-lookup"><span data-stu-id="c99c7-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="c99c7-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c99c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="c99c7-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="c99c7-106">[in] Identifies the domain which has been created.</span><span class="sxs-lookup"><span data-stu-id="c99c7-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c99c7-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span><span class="sxs-lookup"><span data-stu-id="c99c7-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c99c7-108">备注</span><span class="sxs-lookup"><span data-stu-id="c99c7-108">Remarks</span></span>  
 <span data-ttu-id="c99c7-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span><span class="sxs-lookup"><span data-stu-id="c99c7-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="c99c7-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span><span class="sxs-lookup"><span data-stu-id="c99c7-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="c99c7-111">A failure HRESULT in `hrStatus` indicates a failure.</span><span class="sxs-lookup"><span data-stu-id="c99c7-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c99c7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span><span class="sxs-lookup"><span data-stu-id="c99c7-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c99c7-113">要求</span><span class="sxs-lookup"><span data-stu-id="c99c7-113">Requirements</span></span>  
 <span data-ttu-id="c99c7-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c99c7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c99c7-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c99c7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c99c7-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c99c7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c99c7-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c99c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99c7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c99c7-118">See also</span></span>

- [<span data-ttu-id="c99c7-119">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c99c7-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
