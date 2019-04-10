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
ms.openlocfilehash: 4e549e13c0d51e4aa708a674a2224168ab66f8ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178160"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="be4bb-102">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="be4bb-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="be4bb-103">删除公共语言运行时 (CLR) 下载缓存。</span><span class="sxs-lookup"><span data-stu-id="be4bb-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be4bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="be4bb-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="be4bb-105">返回值</span><span class="sxs-lookup"><span data-stu-id="be4bb-105">Return Value</span></span>  
 <span data-ttu-id="be4bb-106">此方法返回标准 COM 错误代码，如在 WinError.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="be4bb-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be4bb-107">备注</span><span class="sxs-lookup"><span data-stu-id="be4bb-107">Remarks</span></span>  
 <span data-ttu-id="be4bb-108">CLR 下载缓存是从某个 URL 下载强名称的程序集可能重复使用的存储位置的区域。</span><span class="sxs-lookup"><span data-stu-id="be4bb-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be4bb-109">要求</span><span class="sxs-lookup"><span data-stu-id="be4bb-109">Requirements</span></span>  
 <span data-ttu-id="be4bb-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be4bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be4bb-111">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="be4bb-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="be4bb-112">**库：** Fusion.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="be4bb-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="be4bb-113">使用而不是 Mscorwks.dll Fusion.dll 确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="be4bb-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="be4bb-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="be4bb-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be4bb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="be4bb-115">See also</span></span>

- [<span data-ttu-id="be4bb-116">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="be4bb-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="be4bb-117">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="be4bb-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="be4bb-118">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="be4bb-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
