---
title: ClrCreateManagedInstance 函数
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67bd6e8a0519d35b867cb525d5ff7730c0459016
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490683"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="84a5e-102">ClrCreateManagedInstance 函数</span><span class="sxs-lookup"><span data-stu-id="84a5e-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="84a5e-103">创建指定的托管类型的实例。</span><span class="sxs-lookup"><span data-stu-id="84a5e-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="84a5e-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="84a5e-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="84a5e-105">使用 COM 激活来创建的托管类型的实例或使用托管 (请参阅[CLR 承载接口中添加.NET Framework 4 和 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md))。</span><span class="sxs-lookup"><span data-stu-id="84a5e-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a5e-106">语法</span><span class="sxs-lookup"><span data-stu-id="84a5e-106">Syntax</span></span>  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84a5e-107">参数</span><span class="sxs-lookup"><span data-stu-id="84a5e-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="84a5e-108">[in]指向所请求的实例类型的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="84a5e-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="84a5e-109">[in]`IID`的所请求的实例类型。</span><span class="sxs-lookup"><span data-stu-id="84a5e-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="84a5e-110">[out]指向由调用方请求的托管类型的实例的指针指向的指针。</span><span class="sxs-lookup"><span data-stu-id="84a5e-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84a5e-111">备注</span><span class="sxs-lookup"><span data-stu-id="84a5e-111">Remarks</span></span>  
 <span data-ttu-id="84a5e-112">公共语言运行时应该已经加载到进程。</span><span class="sxs-lookup"><span data-stu-id="84a5e-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="84a5e-113">例如，它可以通过调用由加载[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数之前`ClrCreateManagedInstance`调用函数。</span><span class="sxs-lookup"><span data-stu-id="84a5e-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="84a5e-114">如果未加载运行时，`ClrCreateManagedInstance`首次尝试加载 v1.0.3705 的运行时。</span><span class="sxs-lookup"><span data-stu-id="84a5e-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="84a5e-115">如果失败，它尝试加载运行时的最新版本。</span><span class="sxs-lookup"><span data-stu-id="84a5e-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84a5e-116">要求</span><span class="sxs-lookup"><span data-stu-id="84a5e-116">Requirements</span></span>  
 <span data-ttu-id="84a5e-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84a5e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a5e-118">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="84a5e-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84a5e-119">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84a5e-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84a5e-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a5e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a5e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="84a5e-121">See also</span></span>

- [<span data-ttu-id="84a5e-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="84a5e-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="84a5e-123">承载</span><span class="sxs-lookup"><span data-stu-id="84a5e-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
