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
ms.openlocfilehash: 5f2a05009caed7bef6da9edee57a4a54b876b18f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580962"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="769a1-102">CorLaunchApplication 函数</span><span class="sxs-lookup"><span data-stu-id="769a1-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="769a1-103">启动指定的网络路径，使用指定的清单和其他应用程序数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="769a1-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="769a1-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="769a1-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769a1-105">语法</span><span class="sxs-lookup"><span data-stu-id="769a1-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="769a1-106">参数</span><span class="sxs-lookup"><span data-stu-id="769a1-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="769a1-107">[in]值为[HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md)枚举，用于指定的启动应用程序的宿主类型。</span><span class="sxs-lookup"><span data-stu-id="769a1-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="769a1-108">[in]正在启动的应用程序的全名。</span><span class="sxs-lookup"><span data-stu-id="769a1-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="769a1-109">[in]应用程序的清单路径数。</span><span class="sxs-lookup"><span data-stu-id="769a1-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="769a1-110">[in]一个字符串数组，其中每个指定要启动的应用程序清单的路径。</span><span class="sxs-lookup"><span data-stu-id="769a1-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="769a1-111">[in]正在启动的应用程序的激活数据项目数。</span><span class="sxs-lookup"><span data-stu-id="769a1-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="769a1-112">[in]一个字符串数组，其中每个是要启动的应用程序的激活数据项。</span><span class="sxs-lookup"><span data-stu-id="769a1-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="769a1-113">[out]指向有关在其中加载应用程序过程的信息的指针。</span><span class="sxs-lookup"><span data-stu-id="769a1-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="769a1-114">要求</span><span class="sxs-lookup"><span data-stu-id="769a1-114">Requirements</span></span>  
 <span data-ttu-id="769a1-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="769a1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="769a1-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="769a1-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="769a1-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="769a1-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="769a1-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="769a1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769a1-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="769a1-119">See also</span></span>
- [<span data-ttu-id="769a1-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="769a1-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
