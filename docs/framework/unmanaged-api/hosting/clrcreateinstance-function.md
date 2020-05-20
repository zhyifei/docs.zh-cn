---
title: CLRCreateInstance 函数
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
ms.openlocfilehash: c3011149b9b23e776ad3baac9e41f3c42213654d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616822"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="05466-102">CLRCreateInstance 函数</span><span class="sxs-lookup"><span data-stu-id="05466-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="05466-103">提供以下三个接口之一： [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)、 [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)或[ICLRDebugging](../debugging/iclrdebugging-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="05466-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05466-104">语法</span><span class="sxs-lookup"><span data-stu-id="05466-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05466-105">参数</span><span class="sxs-lookup"><span data-stu-id="05466-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="05466-106">中三个类标识符之一： CLSID_CLRMetaHost、CLSID_CLRMetaHostPolicy 或 CLSID_CLRDebugging。</span><span class="sxs-lookup"><span data-stu-id="05466-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="05466-107">中三个接口标识符（Iid）之一： IID_ICLRMetaHost、IID_ICLRMetaHostPolicy 或 IID_ICLRDebugging。</span><span class="sxs-lookup"><span data-stu-id="05466-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="05466-108">弄以下三个接口之一： [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)、 [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)或[ICLRDebugging](../debugging/iclrdebugging-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="05466-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05466-109">返回值</span><span class="sxs-lookup"><span data-stu-id="05466-109">Return Value</span></span>  
 <span data-ttu-id="05466-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="05466-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="05466-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05466-111">HRESULT</span></span>|<span data-ttu-id="05466-112">说明</span><span class="sxs-lookup"><span data-stu-id="05466-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05466-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="05466-113">S_OK</span></span>|<span data-ttu-id="05466-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="05466-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="05466-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="05466-115">E_POINTER</span></span>|<span data-ttu-id="05466-116">`ppInterface` 为 null。</span><span class="sxs-lookup"><span data-stu-id="05466-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05466-117">备注</span><span class="sxs-lookup"><span data-stu-id="05466-117">Remarks</span></span>  
 <span data-ttu-id="05466-118">下表显示了和支持的组合 `clsid` `riid` 。</span><span class="sxs-lookup"><span data-stu-id="05466-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="05466-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="05466-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="05466-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="05466-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="05466-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="05466-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="05466-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="05466-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="05466-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="05466-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="05466-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="05466-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="05466-125">下面的代码演示如何使用 `CLRCreateInstance` 获取所有三个接口：</span><span class="sxs-lookup"><span data-stu-id="05466-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```cpp  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="05466-126">要求</span><span class="sxs-lookup"><span data-stu-id="05466-126">Requirements</span></span>  
 <span data-ttu-id="05466-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05466-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05466-128">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="05466-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="05466-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="05466-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05466-130">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05466-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05466-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05466-131">See also</span></span>

- [<span data-ttu-id="05466-132">承载</span><span class="sxs-lookup"><span data-stu-id="05466-132">Hosting</span></span>](index.md)
