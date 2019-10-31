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
ms.openlocfilehash: 4e672030ae83b57da6f9ab66630513d79f28b8f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131991"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="daf85-102">ClrCreateManagedInstance 函数</span><span class="sxs-lookup"><span data-stu-id="daf85-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="daf85-103">创建指定托管类型的实例。</span><span class="sxs-lookup"><span data-stu-id="daf85-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="daf85-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="daf85-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="daf85-105">使用 COM 激活创建托管类型的实例，或使用宿主（请参阅[.NET Framework 4 和4.5 中添加的 CLR 承载接口](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)）。</span><span class="sxs-lookup"><span data-stu-id="daf85-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf85-106">语法</span><span class="sxs-lookup"><span data-stu-id="daf85-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daf85-107">参数</span><span class="sxs-lookup"><span data-stu-id="daf85-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="daf85-108">中一个指针，指向所请求的实例类型的名称。</span><span class="sxs-lookup"><span data-stu-id="daf85-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="daf85-109">中请求的实例类型的 `IID`。</span><span class="sxs-lookup"><span data-stu-id="daf85-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="daf85-110">弄指向调用方请求的托管类型实例的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="daf85-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daf85-111">备注</span><span class="sxs-lookup"><span data-stu-id="daf85-111">Remarks</span></span>  
 <span data-ttu-id="daf85-112">公共语言运行时应已加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="daf85-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="daf85-113">例如，在调用 `ClrCreateManagedInstance` 函数之前，可以使用对[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数的调用来加载该函数。</span><span class="sxs-lookup"><span data-stu-id="daf85-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="daf85-114">如果未加载运行时，`ClrCreateManagedInstance` 首先尝试加载运行时的 v1.0.3705。</span><span class="sxs-lookup"><span data-stu-id="daf85-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="daf85-115">如果失败，它将尝试加载最新版本的运行时。</span><span class="sxs-lookup"><span data-stu-id="daf85-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf85-116">要求</span><span class="sxs-lookup"><span data-stu-id="daf85-116">Requirements</span></span>  
 <span data-ttu-id="daf85-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="daf85-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf85-118">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="daf85-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="daf85-119">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="daf85-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daf85-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf85-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf85-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="daf85-121">See also</span></span>

- [<span data-ttu-id="daf85-122">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="daf85-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="daf85-123">承载</span><span class="sxs-lookup"><span data-stu-id="daf85-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
