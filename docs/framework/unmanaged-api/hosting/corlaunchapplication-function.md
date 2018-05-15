---
title: CorLaunchApplication 函数
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a53b0a9cdcec33846f9d491e7d6567bcf9235b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="31d1d-102">CorLaunchApplication 函数</span><span class="sxs-lookup"><span data-stu-id="31d1d-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="31d1d-103">启动位于指定的网络路径，使用指定的清单和其他应用程序数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="31d1d-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="31d1d-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="31d1d-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d1d-105">语法</span><span class="sxs-lookup"><span data-stu-id="31d1d-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31d1d-106">参数</span><span class="sxs-lookup"><span data-stu-id="31d1d-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="31d1d-107">[in]值为[HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)枚举，它指定的启动应用程序的宿主类型。</span><span class="sxs-lookup"><span data-stu-id="31d1d-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="31d1d-108">[in]正在启动应用程序的完整名称。</span><span class="sxs-lookup"><span data-stu-id="31d1d-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="31d1d-109">[in]应用程序的清单路径的数量。</span><span class="sxs-lookup"><span data-stu-id="31d1d-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="31d1d-110">[in]一个字符串数组，其中每个指定的应用程序正在启动清单的路径。</span><span class="sxs-lookup"><span data-stu-id="31d1d-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="31d1d-111">[in]激活的应用程序正在启动的数据项目数。</span><span class="sxs-lookup"><span data-stu-id="31d1d-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="31d1d-112">[in]一个字符串数组，其中每个是正在启动该应用程序的激活数据项。</span><span class="sxs-lookup"><span data-stu-id="31d1d-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="31d1d-113">[out]有关应用程序加载的过程的信息指向的指针。</span><span class="sxs-lookup"><span data-stu-id="31d1d-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d1d-114">要求</span><span class="sxs-lookup"><span data-stu-id="31d1d-114">Requirements</span></span>  
 <span data-ttu-id="31d1d-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31d1d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d1d-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="31d1d-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31d1d-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="31d1d-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31d1d-118">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d1d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d1d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="31d1d-119">See Also</span></span>  
 [<span data-ttu-id="31d1d-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="31d1d-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
