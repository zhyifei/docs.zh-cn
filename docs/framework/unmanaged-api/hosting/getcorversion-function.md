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
ms.openlocfilehash: 4bd398a5b214ac0046d5fe1965f70eef2eedaa6b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490399"
---
# <a name="getcorversion-function"></a><span data-ttu-id="7d251-102">GetCORVersion 函数</span><span class="sxs-lookup"><span data-stu-id="7d251-102">GetCORVersion Function</span></span>
<span data-ttu-id="7d251-103">返回在当前进程中运行公共语言运行时 (CLR) 的版本号。</span><span class="sxs-lookup"><span data-stu-id="7d251-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="7d251-104">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="7d251-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d251-105">语法</span><span class="sxs-lookup"><span data-stu-id="7d251-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="7d251-106">参数</span><span class="sxs-lookup"><span data-stu-id="7d251-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="7d251-107">指向 CLR 中返回一个字符串，指定当前加载到进程的运行时版本的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="7d251-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="7d251-108">返回的字符串采用相同的形式为字符串传递给[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)，例如，"v1.0.1216"。</span><span class="sxs-lookup"><span data-stu-id="7d251-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="7d251-109">如果尚未在流程中加载运行时，函数将返回在计算机上安装的运行时的最新版本的相应的目录信息。</span><span class="sxs-lookup"><span data-stu-id="7d251-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7d251-110">字符数 (`WCHAR`s)，则可保存在`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="7d251-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7d251-111">指向实际返回中的字符数的`pbuffer`。</span><span class="sxs-lookup"><span data-stu-id="7d251-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="7d251-112">如果`pbuffer`是 null 指针，则运行时返回 E_POINTER。</span><span class="sxs-lookup"><span data-stu-id="7d251-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="7d251-113">如果字符数大于的长度`pbuffer`，运行时将返回 ERROR_INSUFFICIENT_BUFFER。</span><span class="sxs-lookup"><span data-stu-id="7d251-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d251-114">要求</span><span class="sxs-lookup"><span data-stu-id="7d251-114">Requirements</span></span>  
 <span data-ttu-id="7d251-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d251-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d251-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7d251-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d251-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d251-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d251-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d251-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d251-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d251-119">See also</span></span>

- [<span data-ttu-id="7d251-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="7d251-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
