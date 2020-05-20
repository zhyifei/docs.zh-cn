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
ms.openlocfilehash: e8945d40a3761ec51a73a8ae90ddc1d84ccab651
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616861"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="92340-102">CallFunctionShim 函数</span><span class="sxs-lookup"><span data-stu-id="92340-102">CallFunctionShim Function</span></span>
<span data-ttu-id="92340-103">对指定库中具有指定名称和参数的函数进行调用。</span><span class="sxs-lookup"><span data-stu-id="92340-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="92340-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="92340-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92340-105">语法</span><span class="sxs-lookup"><span data-stu-id="92340-105">Syntax</span></span>  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92340-106">参数</span><span class="sxs-lookup"><span data-stu-id="92340-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="92340-107">中包含函数的库的名称。</span><span class="sxs-lookup"><span data-stu-id="92340-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="92340-108">中函数的名称。</span><span class="sxs-lookup"><span data-stu-id="92340-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="92340-109">中要传递给函数的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="92340-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="92340-110">中要传递给函数的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="92340-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="92340-111">中包含函数的库的版本。</span><span class="sxs-lookup"><span data-stu-id="92340-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="92340-112">中保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="92340-112">[in] Reserved for future use.</span></span> <span data-ttu-id="92340-113">在此参数中传递零。</span><span class="sxs-lookup"><span data-stu-id="92340-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92340-114">要求</span><span class="sxs-lookup"><span data-stu-id="92340-114">Requirements</span></span>  
 <span data-ttu-id="92340-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92340-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92340-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="92340-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92340-117">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="92340-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92340-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92340-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92340-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92340-119">See also</span></span>

- [<span data-ttu-id="92340-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="92340-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
