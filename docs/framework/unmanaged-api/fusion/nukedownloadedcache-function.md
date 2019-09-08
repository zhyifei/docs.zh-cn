---
title: NukeDownloadedCache 函数
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796305"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="3fa4c-102">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="3fa4c-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="3fa4c-103">删除公共语言运行时（CLR）下载缓存。</span><span class="sxs-lookup"><span data-stu-id="3fa4c-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa4c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fa4c-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3fa4c-105">返回值</span><span class="sxs-lookup"><span data-stu-id="3fa4c-105">Return Value</span></span>  
 <span data-ttu-id="3fa4c-106">此方法返回 Winerror.h 中定义的标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="3fa4c-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fa4c-107">备注</span><span class="sxs-lookup"><span data-stu-id="3fa4c-107">Remarks</span></span>  
 <span data-ttu-id="3fa4c-108">CLR 下载缓存是存储从 URL 下载的具有强名称的程序集以便可以重复使用的区域。</span><span class="sxs-lookup"><span data-stu-id="3fa4c-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fa4c-109">要求</span><span class="sxs-lookup"><span data-stu-id="3fa4c-109">Requirements</span></span>  
 <span data-ttu-id="3fa4c-110">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fa4c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fa4c-111">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="3fa4c-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3fa4c-112">**类库**合成 .dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="3fa4c-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="3fa4c-113">使用 Mscorwks.dll 而不是来确保目标为正确的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="3fa4c-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="3fa4c-114">**.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fa4c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa4c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fa4c-115">See also</span></span>

- [<span data-ttu-id="3fa4c-116">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="3fa4c-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="3fa4c-117">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="3fa4c-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="3fa4c-118">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="3fa4c-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
