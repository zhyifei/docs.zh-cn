---
title: ICLRRuntimeInfo::GetProcAddress 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: cedda39aeebc62c6bf43f42ae2daf6f6f515fd27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120270"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="43819-102">ICLRRuntimeInfo::GetProcAddress 方法</span><span class="sxs-lookup"><span data-stu-id="43819-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="43819-103">获取从与此接口关联的公共语言运行时（CLR）导出的指定函数的地址。</span><span class="sxs-lookup"><span data-stu-id="43819-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="43819-104">此方法取代了[GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="43819-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43819-105">语法</span><span class="sxs-lookup"><span data-stu-id="43819-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43819-106">参数</span><span class="sxs-lookup"><span data-stu-id="43819-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="43819-107">中导出的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="43819-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="43819-108">弄导出函数的地址。</span><span class="sxs-lookup"><span data-stu-id="43819-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43819-109">返回值</span><span class="sxs-lookup"><span data-stu-id="43819-109">Return Value</span></span>  
 <span data-ttu-id="43819-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="43819-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="43819-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43819-111">HRESULT</span></span>|<span data-ttu-id="43819-112">描述</span><span class="sxs-lookup"><span data-stu-id="43819-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43819-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="43819-113">S_OK</span></span>|<span data-ttu-id="43819-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="43819-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="43819-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="43819-115">E_POINTER</span></span>|<span data-ttu-id="43819-116">`pszProcName` 或 `ppProc` 为 null。</span><span class="sxs-lookup"><span data-stu-id="43819-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="43819-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="43819-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="43819-118">指定的函数不是已导出的函数。</span><span class="sxs-lookup"><span data-stu-id="43819-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43819-119">备注</span><span class="sxs-lookup"><span data-stu-id="43819-119">Remarks</span></span>  
 <span data-ttu-id="43819-120">此方法导致加载但不初始化 CLR。</span><span class="sxs-lookup"><span data-stu-id="43819-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43819-121">要求</span><span class="sxs-lookup"><span data-stu-id="43819-121">Requirements</span></span>  
 <span data-ttu-id="43819-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43819-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43819-123">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="43819-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="43819-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="43819-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43819-125">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43819-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43819-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="43819-126">See also</span></span>

- [<span data-ttu-id="43819-127">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="43819-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="43819-128">承载接口</span><span class="sxs-lookup"><span data-stu-id="43819-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="43819-129">承载</span><span class="sxs-lookup"><span data-stu-id="43819-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
