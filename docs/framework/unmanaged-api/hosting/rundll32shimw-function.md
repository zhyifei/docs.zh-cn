---
title: RunDll32ShimW 函数
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccfdf9ffab35f076b85c067c2b412020a5f541b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231079"
---
# <a name="rundll32shimw-function"></a><span data-ttu-id="fc95f-102">RunDll32ShimW 函数</span><span class="sxs-lookup"><span data-stu-id="fc95f-102">RunDll32ShimW Function</span></span>
<span data-ttu-id="fc95f-103">执行指定的命令。</span><span class="sxs-lookup"><span data-stu-id="fc95f-103">Executes the specified command.</span></span>  
  
 <span data-ttu-id="fc95f-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc95f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc95f-105">语法</span><span class="sxs-lookup"><span data-stu-id="fc95f-105">Syntax</span></span>  
  
```  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc95f-106">参数</span><span class="sxs-lookup"><span data-stu-id="fc95f-106">Parameters</span></span>  
 `hwnd`  
 <span data-ttu-id="fc95f-107">[in]将在其中显示命令输出窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="fc95f-107">[in] A handle to a window in which the command output will be displayed.</span></span>  
  
 `hinst`  
 <span data-ttu-id="fc95f-108">[in]包含该命令的库句柄。</span><span class="sxs-lookup"><span data-stu-id="fc95f-108">[in] A handle to the library that contains the command.</span></span>  
  
 `lpszCmdLine`  
 <span data-ttu-id="fc95f-109">[in]一个字符串，指定要执行的命令。</span><span class="sxs-lookup"><span data-stu-id="fc95f-109">[in] A string that specifies the command to be executed.</span></span>  
  
 `nCmdShow`  
 <span data-ttu-id="fc95f-110">[in]一个整数，指定的输出窗口的显示模式。</span><span class="sxs-lookup"><span data-stu-id="fc95f-110">[in] An integer that specifies the display mode for the output window.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc95f-111">要求</span><span class="sxs-lookup"><span data-stu-id="fc95f-111">Requirements</span></span>  
 <span data-ttu-id="fc95f-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc95f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc95f-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc95f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc95f-114">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc95f-114">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fc95f-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fc95f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc95f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc95f-116">See also</span></span>

- [<span data-ttu-id="fc95f-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="fc95f-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
