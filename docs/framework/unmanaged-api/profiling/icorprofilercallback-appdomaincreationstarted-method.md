---
title: "ICorProfilerCallback::AppDomainCreationStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 395664081460677c4d2b94fc5478513ce239c5be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="c2662-102">ICorProfilerCallback::AppDomainCreationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="c2662-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="c2662-103">通知探查器创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c2662-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2662-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2662-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2662-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2662-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="c2662-106">[in]标识正在创建的域。</span><span class="sxs-lookup"><span data-stu-id="c2662-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2662-107">备注</span><span class="sxs-lookup"><span data-stu-id="c2662-107">Remarks</span></span>  
 <span data-ttu-id="c2662-108">ID 不是有效的任何信息请求到[icorprofilercallback:: Appdomaincreationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)调用方法。</span><span class="sxs-lookup"><span data-stu-id="c2662-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2662-109">要求</span><span class="sxs-lookup"><span data-stu-id="c2662-109">Requirements</span></span>  
 <span data-ttu-id="c2662-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2662-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2662-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2662-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2662-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2662-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2662-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2662-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2662-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2662-114">See Also</span></span>  
 [<span data-ttu-id="c2662-115">ICorProfilerCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c2662-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
