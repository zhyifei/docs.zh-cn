---
title: GetHistoryFileDirectory 函数
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21742881c5aef7384be318297aa3432411c3d57c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479276"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="abad6-102">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="abad6-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="abad6-103">检索应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="abad6-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abad6-104">语法</span><span class="sxs-lookup"><span data-stu-id="abad6-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abad6-105">参数</span><span class="sxs-lookup"><span data-stu-id="abad6-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="abad6-106">[out]一个缓冲区来存放到应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="abad6-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="abad6-107">[in、 out]缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="abad6-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abad6-108">返回值</span><span class="sxs-lookup"><span data-stu-id="abad6-108">Return Value</span></span>  
 <span data-ttu-id="abad6-109">除了以下值在 WinError.h 文件中定义，此方法将返回标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="abad6-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="abad6-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="abad6-110">Return code</span></span>|<span data-ttu-id="abad6-111">描述</span><span class="sxs-lookup"><span data-stu-id="abad6-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="abad6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="abad6-112">S_OK</span></span>|<span data-ttu-id="abad6-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="abad6-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="abad6-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="abad6-114">E_INVALIDARG</span></span>|<span data-ttu-id="abad6-115">`wzDir` 或`pdwSize`是 null 或版本字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="abad6-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abad6-116">备注</span><span class="sxs-lookup"><span data-stu-id="abad6-116">Remarks</span></span>  
 <span data-ttu-id="abad6-117">成功完成后，`pdwSize`参数设置为路径字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="abad6-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abad6-118">要求</span><span class="sxs-lookup"><span data-stu-id="abad6-118">Requirements</span></span>  
 <span data-ttu-id="abad6-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abad6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abad6-120">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="abad6-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="abad6-121">**库：** Fusion.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="abad6-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="abad6-122">使用而不是 Mscorwks.dll Fusion.dll 确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="abad6-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="abad6-123">**.NET Framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abad6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abad6-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="abad6-124">See also</span></span>
- [<span data-ttu-id="abad6-125">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="abad6-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="abad6-126">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="abad6-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [<span data-ttu-id="abad6-127">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="abad6-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
