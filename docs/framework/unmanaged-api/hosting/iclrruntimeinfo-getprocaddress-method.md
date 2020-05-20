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
ms.openlocfilehash: 2690a5c2e7c499d68ef9e903c62bff8f85e72e8e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703865"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="f8bfa-102">ICLRRuntimeInfo::GetProcAddress 方法</span><span class="sxs-lookup"><span data-stu-id="f8bfa-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="f8bfa-103">获取从与此接口关联的公共语言运行时（CLR）导出的指定函数的地址。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="f8bfa-104">此方法取代了[GetRealProcAddress](getrealprocaddress-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8bfa-105">语法</span><span class="sxs-lookup"><span data-stu-id="f8bfa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8bfa-106">参数</span><span class="sxs-lookup"><span data-stu-id="f8bfa-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="f8bfa-107">中导出的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="f8bfa-108">弄导出函数的地址。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8bfa-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f8bfa-109">Return Value</span></span>  
 <span data-ttu-id="f8bfa-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f8bfa-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8bfa-111">HRESULT</span></span>|<span data-ttu-id="f8bfa-112">说明</span><span class="sxs-lookup"><span data-stu-id="f8bfa-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8bfa-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8bfa-113">S_OK</span></span>|<span data-ttu-id="f8bfa-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f8bfa-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f8bfa-115">E_POINTER</span></span>|<span data-ttu-id="f8bfa-116">`pszProcName` 或 `ppProc` 为 null。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="f8bfa-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="f8bfa-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="f8bfa-118">指定的函数不是已导出的函数。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8bfa-119">备注</span><span class="sxs-lookup"><span data-stu-id="f8bfa-119">Remarks</span></span>  
 <span data-ttu-id="f8bfa-120">此方法导致加载但不初始化 CLR。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8bfa-121">要求</span><span class="sxs-lookup"><span data-stu-id="f8bfa-121">Requirements</span></span>  
 <span data-ttu-id="f8bfa-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8bfa-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8bfa-123">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="f8bfa-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f8bfa-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f8bfa-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8bfa-125">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8bfa-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8bfa-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8bfa-126">See also</span></span>

- [<span data-ttu-id="f8bfa-127">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f8bfa-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f8bfa-128">承载接口</span><span class="sxs-lookup"><span data-stu-id="f8bfa-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f8bfa-129">承载</span><span class="sxs-lookup"><span data-stu-id="f8bfa-129">Hosting</span></span>](index.md)
