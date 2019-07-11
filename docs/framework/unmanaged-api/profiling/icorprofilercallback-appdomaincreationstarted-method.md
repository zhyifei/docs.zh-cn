---
title: ICorProfilerCallback::AppDomainCreationStarted 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 17f7c985b27adbbb2a5c7ddc2bb62fc93a099a45
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763127"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="8270e-102">ICorProfilerCallback::AppDomainCreationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="8270e-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="8270e-103">通知探查器正在创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="8270e-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8270e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8270e-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8270e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8270e-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="8270e-106">[in]标识正在创建的域。</span><span class="sxs-lookup"><span data-stu-id="8270e-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8270e-107">备注</span><span class="sxs-lookup"><span data-stu-id="8270e-107">Remarks</span></span>  
 <span data-ttu-id="8270e-108">ID 不是有效的任何信息请求，直到[icorprofilercallback:: Appdomaincreationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="8270e-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8270e-109">要求</span><span class="sxs-lookup"><span data-stu-id="8270e-109">Requirements</span></span>  
 <span data-ttu-id="8270e-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8270e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8270e-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8270e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8270e-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8270e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8270e-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8270e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8270e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8270e-114">See also</span></span>

- [<span data-ttu-id="8270e-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8270e-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
