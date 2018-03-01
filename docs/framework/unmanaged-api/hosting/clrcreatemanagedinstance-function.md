---
title: "ClrCreateManagedInstance 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64a1bc6bbd89e3a36ac53b322bb246a7e61baa67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="657ee-102">ClrCreateManagedInstance 函数</span><span class="sxs-lookup"><span data-stu-id="657ee-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="657ee-103">创建指定的托管类型的实例。</span><span class="sxs-lookup"><span data-stu-id="657ee-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="657ee-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="657ee-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="657ee-105">使用 COM 激活创建的托管类型实例或使用承载 (请参阅[CLR 承载接口添加在.NET Framework 4 和 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md))。</span><span class="sxs-lookup"><span data-stu-id="657ee-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="657ee-106">语法</span><span class="sxs-lookup"><span data-stu-id="657ee-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="657ee-107">参数</span><span class="sxs-lookup"><span data-stu-id="657ee-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="657ee-108">[in]指向所请求的实例类型的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="657ee-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="657ee-109">[in]`IID`正在请求的实例类型。</span><span class="sxs-lookup"><span data-stu-id="657ee-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="657ee-110">[out]指向由调用方请求的托管类型的实例的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="657ee-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="657ee-111">备注</span><span class="sxs-lookup"><span data-stu-id="657ee-111">Remarks</span></span>  
 <span data-ttu-id="657ee-112">公共语言运行时应已加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="657ee-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="657ee-113">例如，可以通过调用加载它[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数之前`ClrCreateManagedInstance`调用函数。</span><span class="sxs-lookup"><span data-stu-id="657ee-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="657ee-114">如果未加载运行时，`ClrCreateManagedInstance`首次尝试加载的运行时的 v1.0.3705。</span><span class="sxs-lookup"><span data-stu-id="657ee-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="657ee-115">如果该操作失败，它尝试加载运行时的最新版本。</span><span class="sxs-lookup"><span data-stu-id="657ee-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="657ee-116">惠?</span><span class="sxs-lookup"><span data-stu-id="657ee-116">Requirements</span></span>  
 <span data-ttu-id="657ee-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="657ee-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="657ee-118">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="657ee-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="657ee-119">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="657ee-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="657ee-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="657ee-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657ee-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="657ee-121">See Also</span></span>  
 [<span data-ttu-id="657ee-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="657ee-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="657ee-123">承载</span><span class="sxs-lookup"><span data-stu-id="657ee-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
