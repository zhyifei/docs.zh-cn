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
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178192"
---
# <a name="getcorversion-function"></a><span data-ttu-id="e719e-102">GetCORVersion 函数</span><span class="sxs-lookup"><span data-stu-id="e719e-102">GetCORVersion Function</span></span>
<span data-ttu-id="e719e-103">返回当前进程中运行的通用语言运行时 （CLR） 的版本号。</span><span class="sxs-lookup"><span data-stu-id="e719e-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="e719e-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="e719e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e719e-105">语法</span><span class="sxs-lookup"><span data-stu-id="e719e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="e719e-106">parameters</span><span class="sxs-lookup"><span data-stu-id="e719e-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="e719e-107">指向缓冲区的指针，其中 CLR 返回一个字符串，指定当前加载到进程的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="e719e-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="e719e-108">返回的字符串采用与传递给[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)的字符串相同的形式，例如"v1.0.1216"。</span><span class="sxs-lookup"><span data-stu-id="e719e-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="e719e-109">如果运行时尚未加载到进程中，该函数将返回计算机上安装的最新版本的运行时的相应目录信息。</span><span class="sxs-lookup"><span data-stu-id="e719e-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e719e-110">可在 中`pbuffer`持有的字符`WCHAR`数 。</span><span class="sxs-lookup"><span data-stu-id="e719e-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e719e-111">指向 中`pbuffer`实际返回的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="e719e-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="e719e-112">如果`pbuffer`为空指针，则运行时返回E_POINTER。</span><span class="sxs-lookup"><span data-stu-id="e719e-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="e719e-113">如果字符数大于，则`pbuffer`长度 为 ，运行时将返回ERROR_INSUFFICIENT_BUFFER。</span><span class="sxs-lookup"><span data-stu-id="e719e-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e719e-114">要求</span><span class="sxs-lookup"><span data-stu-id="e719e-114">Requirements</span></span>  
 <span data-ttu-id="e719e-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e719e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e719e-116">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e719e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e719e-117">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e719e-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e719e-118">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e719e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e719e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e719e-119">See also</span></span>

- [<span data-ttu-id="e719e-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="e719e-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
