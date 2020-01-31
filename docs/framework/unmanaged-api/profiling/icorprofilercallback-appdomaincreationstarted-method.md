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
ms.openlocfilehash: 49c3ab4901537805a1ae1be79097c55cc331d29d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866708"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="89c1c-102">ICorProfilerCallback::AppDomainCreationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="89c1c-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="89c1c-103">通知探查器正在创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="89c1c-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="89c1c-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89c1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="89c1c-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="89c1c-106">\[中的] 标识正在创建的域。</span><span class="sxs-lookup"><span data-stu-id="89c1c-106">\[in] Identifies the domain which is being created.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="89c1c-107">备注</span><span class="sxs-lookup"><span data-stu-id="89c1c-107">Remarks</span></span>  
 <span data-ttu-id="89c1c-108">在调用[ICorProfilerCallback：： AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md)方法之前，ID 对任何信息请求都无效。</span><span class="sxs-lookup"><span data-stu-id="89c1c-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89c1c-109">需求</span><span class="sxs-lookup"><span data-stu-id="89c1c-109">Requirements</span></span>  
 <span data-ttu-id="89c1c-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89c1c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89c1c-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89c1c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89c1c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89c1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89c1c-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c1c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c1c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89c1c-114">See also</span></span>

- [<span data-ttu-id="89c1c-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="89c1c-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
