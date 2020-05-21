---
title: ICLRRuntimeInfo::LoadLibrary 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 09c80c3a56d86943ebe00e5222bb5452ab44e150
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762170"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="2e9a2-102">ICLRRuntimeInfo::LoadLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="2e9a2-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="2e9a2-103">从[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)接口表示的公共语言运行时（CLR）加载 .NET Framework 库。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="2e9a2-104">此方法取代了[LoadLibraryShim](loadlibraryshim-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e9a2-105">语法</span><span class="sxs-lookup"><span data-stu-id="2e9a2-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e9a2-106">参数</span><span class="sxs-lookup"><span data-stu-id="2e9a2-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="2e9a2-107">中要加载的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="2e9a2-108">弄已加载的程序集的句柄。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e9a2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2e9a2-109">Return Value</span></span>  
 <span data-ttu-id="2e9a2-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2e9a2-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e9a2-111">HRESULT</span></span>|<span data-ttu-id="2e9a2-112">说明</span><span class="sxs-lookup"><span data-stu-id="2e9a2-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e9a2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e9a2-113">S_OK</span></span>|<span data-ttu-id="2e9a2-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="2e9a2-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2e9a2-115">E_POINTER</span></span>|<span data-ttu-id="2e9a2-116">`pwzDllName` 或 `phndModule` 为 null。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="2e9a2-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2e9a2-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2e9a2-118">没有足够的内存可用来处理请求。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e9a2-119">注解</span><span class="sxs-lookup"><span data-stu-id="2e9a2-119">Remarks</span></span>  
 <span data-ttu-id="2e9a2-120">此方法仅加载 .NET Framework 可再发行组件包中包含的 Dll。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="2e9a2-121">它无法加载用户生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e9a2-122">要求</span><span class="sxs-lookup"><span data-stu-id="2e9a2-122">Requirements</span></span>  
 <span data-ttu-id="2e9a2-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e9a2-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e9a2-124">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="2e9a2-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2e9a2-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="2e9a2-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e9a2-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e9a2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9a2-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e9a2-127">See also</span></span>

- [<span data-ttu-id="2e9a2-128">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="2e9a2-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="2e9a2-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="2e9a2-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="2e9a2-130">承载</span><span class="sxs-lookup"><span data-stu-id="2e9a2-130">Hosting</span></span>](index.md)
