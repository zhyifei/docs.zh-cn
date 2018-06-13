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
ms.openlocfilehash: 1060ca140db0304c8e5667f7fdf9624b3ac2b64a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429278"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="73e65-102">CallFunctionShim 函数</span><span class="sxs-lookup"><span data-stu-id="73e65-102">CallFunctionShim Function</span></span>
<span data-ttu-id="73e65-103">将指定的库中具有指定的名称和参数的函数调用。</span><span class="sxs-lookup"><span data-stu-id="73e65-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="73e65-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="73e65-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e65-105">语法</span><span class="sxs-lookup"><span data-stu-id="73e65-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="73e65-106">参数</span><span class="sxs-lookup"><span data-stu-id="73e65-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="73e65-107">[in]包含函数的库的名称。</span><span class="sxs-lookup"><span data-stu-id="73e65-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="73e65-108">[in]函数的名称。</span><span class="sxs-lookup"><span data-stu-id="73e65-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="73e65-109">[in]要传递给函数的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="73e65-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="73e65-110">[in]要传递给函数的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="73e65-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="73e65-111">[in]包含函数的库的版本。</span><span class="sxs-lookup"><span data-stu-id="73e65-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="73e65-112">[in]留待将来使用。</span><span class="sxs-lookup"><span data-stu-id="73e65-112">[in] Reserved for future use.</span></span> <span data-ttu-id="73e65-113">传递此参数中的零。</span><span class="sxs-lookup"><span data-stu-id="73e65-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73e65-114">要求</span><span class="sxs-lookup"><span data-stu-id="73e65-114">Requirements</span></span>  
 <span data-ttu-id="73e65-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73e65-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73e65-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73e65-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73e65-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73e65-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73e65-118">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73e65-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e65-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="73e65-119">See Also</span></span>  
 [<span data-ttu-id="73e65-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="73e65-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
