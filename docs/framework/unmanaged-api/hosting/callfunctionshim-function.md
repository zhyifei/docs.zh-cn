---
title: CallFunctionShim 函数
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7aeb813cafbf5b18739c4574c386398ac3c7a77b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180474"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="953df-102">CallFunctionShim 函数</span><span class="sxs-lookup"><span data-stu-id="953df-102">CallFunctionShim Function</span></span>
<span data-ttu-id="953df-103">将指定的库中具有指定的名称和参数的函数调用。</span><span class="sxs-lookup"><span data-stu-id="953df-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="953df-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="953df-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="953df-105">语法</span><span class="sxs-lookup"><span data-stu-id="953df-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="953df-106">参数</span><span class="sxs-lookup"><span data-stu-id="953df-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="953df-107">[in]包含该函数的库的名称。</span><span class="sxs-lookup"><span data-stu-id="953df-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="953df-108">[in]函数的名称。</span><span class="sxs-lookup"><span data-stu-id="953df-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="953df-109">[in]要传递给函数的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="953df-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="953df-110">[in]要传递给函数的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="953df-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="953df-111">[in]包含该函数的库的版本。</span><span class="sxs-lookup"><span data-stu-id="953df-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="953df-112">[in]保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="953df-112">[in] Reserved for future use.</span></span> <span data-ttu-id="953df-113">此参数中传递零。</span><span class="sxs-lookup"><span data-stu-id="953df-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953df-114">要求</span><span class="sxs-lookup"><span data-stu-id="953df-114">Requirements</span></span>  
 <span data-ttu-id="953df-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="953df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="953df-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="953df-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="953df-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="953df-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="953df-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="953df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953df-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="953df-119">See also</span></span>

- [<span data-ttu-id="953df-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="953df-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
