---
title: "GetHistoryFileDirectory 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d0ec18a4f95d0d280a66b3b9d9200c560f5f187
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="72c71-102">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="72c71-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="72c71-103">检索应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="72c71-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72c71-104">语法</span><span class="sxs-lookup"><span data-stu-id="72c71-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72c71-105">参数</span><span class="sxs-lookup"><span data-stu-id="72c71-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="72c71-106">[out]一个缓冲区来保存到应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="72c71-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="72c71-107">[在中，out]缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="72c71-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72c71-108">返回值</span><span class="sxs-lookup"><span data-stu-id="72c71-108">Return Value</span></span>  
 <span data-ttu-id="72c71-109">此方法返回标准的 COM 错误代码，除了以下值 WinError.h 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="72c71-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="72c71-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="72c71-110">Return code</span></span>|<span data-ttu-id="72c71-111">描述</span><span class="sxs-lookup"><span data-stu-id="72c71-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="72c71-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="72c71-112">S_OK</span></span>|<span data-ttu-id="72c71-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="72c71-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="72c71-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="72c71-114">E_INVALIDARG</span></span>|<span data-ttu-id="72c71-115">`wzDir`或`pdwSize`为 null 或版本字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="72c71-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72c71-116">备注</span><span class="sxs-lookup"><span data-stu-id="72c71-116">Remarks</span></span>  
 <span data-ttu-id="72c71-117">在成功完成，`pdwSize`参数设置为路径的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="72c71-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72c71-118">惠?</span><span class="sxs-lookup"><span data-stu-id="72c71-118">Requirements</span></span>  
 <span data-ttu-id="72c71-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72c71-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72c71-120">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="72c71-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="72c71-121">**库：**为 Fusion.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="72c71-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="72c71-122">使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="72c71-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="72c71-123">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72c71-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c71-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="72c71-124">See Also</span></span>  
 [<span data-ttu-id="72c71-125">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="72c71-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="72c71-126">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="72c71-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="72c71-127">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="72c71-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
