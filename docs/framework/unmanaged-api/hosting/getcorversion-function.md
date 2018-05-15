---
title: GetCORVersion 函数
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0e922273a7d4e5b98c1321992e5e89e01adb437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="getcorversion-function"></a><span data-ttu-id="bd926-102">GetCORVersion 函数</span><span class="sxs-lookup"><span data-stu-id="bd926-102">GetCORVersion Function</span></span>
<span data-ttu-id="bd926-103">返回在当前进程中运行公共语言运行时 (CLR) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="bd926-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="bd926-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bd926-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd926-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd926-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd926-106">参数</span><span class="sxs-lookup"><span data-stu-id="bd926-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="bd926-107">指向在 CLR 返回一个字符串，指定当前加载到进程的运行时版本的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="bd926-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="bd926-108">返回的字符串将相同的形式作为字符串传递给[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)，例如，"v1.0.1216"。</span><span class="sxs-lookup"><span data-stu-id="bd926-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="bd926-109">如果尚未到过程加载运行时，函数将返回在计算机上安装的运行时的最新版本的相应目录信息。</span><span class="sxs-lookup"><span data-stu-id="bd926-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="bd926-110">字符数 (`WCHAR`s)，可以保存在`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="bd926-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="bd926-111">指向中实际返回的字符数的指针`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="bd926-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="bd926-112">如果`pbuffer`是 null 指针，则运行时返回 E_POINTER。</span><span class="sxs-lookup"><span data-stu-id="bd926-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="bd926-113">如果字符数大于然后的长度`pbuffer`，则运行时返回 ERROR_INSUFFICIENT_BUFFER。</span><span class="sxs-lookup"><span data-stu-id="bd926-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd926-114">要求</span><span class="sxs-lookup"><span data-stu-id="bd926-114">Requirements</span></span>  
 <span data-ttu-id="bd926-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd926-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd926-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd926-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd926-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd926-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd926-118">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd926-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd926-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd926-119">See Also</span></span>  
 [<span data-ttu-id="bd926-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="bd926-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
