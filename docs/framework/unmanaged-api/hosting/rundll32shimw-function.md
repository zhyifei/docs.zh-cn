---
title: "RunDll32ShimW 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RunDll32ShimW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: RunDll32ShimW
helpviewer_keywords: RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3effcdfb8e418d638f4023746be1f0646eceb8d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="bdf2a-102">RunDll32ShimW 函数</span><span class="sxs-lookup"><span data-stu-id="bdf2a-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="bdf2a-103">执行指定的命令。</span><span class="sxs-lookup"><span data-stu-id="bdf2a-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="bdf2a-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bdf2a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf2a-105">语法</span><span class="sxs-lookup"><span data-stu-id="bdf2a-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bdf2a-106">参数</span><span class="sxs-lookup"><span data-stu-id="bdf2a-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="bdf2a-107">[in]将在其中显示命令输出窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="bdf2a-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="bdf2a-108">[in]包含该命令的库的句柄。</span><span class="sxs-lookup"><span data-stu-id="bdf2a-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="bdf2a-109">[in]一个字符串，指定要执行的命令。</span><span class="sxs-lookup"><span data-stu-id="bdf2a-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="bdf2a-110">[in]一个整数，指定输出窗口的显示模式。</span><span class="sxs-lookup"><span data-stu-id="bdf2a-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf2a-111">要求</span><span class="sxs-lookup"><span data-stu-id="bdf2a-111">Requirements</span></span>  
 <span data-ttu-id="bdf2a-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf2a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdf2a-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bdf2a-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bdf2a-114">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bdf2a-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bdf2a-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdf2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf2a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdf2a-116">See Also</span></span>  
 [<span data-ttu-id="bdf2a-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="bdf2a-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
