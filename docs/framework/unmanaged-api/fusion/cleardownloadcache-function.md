---
title: ClearDownloadCache 函数
ms.date: 03/30/2017
api_name:
- ClearDownloadCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- ClearDownloadCache
helpviewer_keywords:
- ClearDownloadCache function [.NET Framework fusion]
ms.assetid: df7595d1-430f-44b4-8160-4c2ba9df70b1
topic_type:
- apiref
ms.openlocfilehash: 0648ba9a35290543f485a67719c6adfeba9114b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108958"
---
# <a name="cleardownloadcache-function"></a><span data-ttu-id="33734-102">ClearDownloadCache 函数</span><span class="sxs-lookup"><span data-stu-id="33734-102">ClearDownloadCache Function</span></span>
<span data-ttu-id="33734-103">清除已下载程序集的全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="33734-103">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33734-104">语法</span><span class="sxs-lookup"><span data-stu-id="33734-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearDownloadCache ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="33734-105">要求</span><span class="sxs-lookup"><span data-stu-id="33734-105">Requirements</span></span>  
 <span data-ttu-id="33734-106">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33734-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33734-107">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="33734-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="33734-108">**库：** 合成 .dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="33734-108">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="33734-109">使用 Mscorwks.dll 而不是来确保目标为正确的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="33734-109">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="33734-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33734-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33734-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="33734-111">See also</span></span>

- [<span data-ttu-id="33734-112">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="33734-112">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="33734-113">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="33734-113">Global Assembly Cache</span></span>](../../app-domains/gac.md)
