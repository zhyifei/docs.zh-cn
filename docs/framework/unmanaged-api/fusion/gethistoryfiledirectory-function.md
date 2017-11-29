---
title: "GetHistoryFileDirectory 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHistoryFileDirectory
api_location: fusion.dll
api_type: DLLExport
f1_keywords: GetHistoryFileDirectory
helpviewer_keywords: GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f01100140e9e1dd05cb42b3cfe586c5f6462444c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="40819-102">GetHistoryFileDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="40819-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="40819-103">检索应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="40819-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40819-104">语法</span><span class="sxs-lookup"><span data-stu-id="40819-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40819-105">参数</span><span class="sxs-lookup"><span data-stu-id="40819-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="40819-106">[out]一个缓冲区来保存到应用程序历史记录目录的路径。</span><span class="sxs-lookup"><span data-stu-id="40819-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="40819-107">[在中，out]缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="40819-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40819-108">返回值</span><span class="sxs-lookup"><span data-stu-id="40819-108">Return Value</span></span>  
 <span data-ttu-id="40819-109">此方法返回标准的 COM 错误代码，除了以下值 WinError.h 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="40819-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="40819-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="40819-110">Return code</span></span>|<span data-ttu-id="40819-111">描述</span><span class="sxs-lookup"><span data-stu-id="40819-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="40819-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="40819-112">S_OK</span></span>|<span data-ttu-id="40819-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="40819-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="40819-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="40819-114">E_INVALIDARG</span></span>|<span data-ttu-id="40819-115">`wzDir`或`pdwSize`为 null 或版本字符串不正确。</span><span class="sxs-lookup"><span data-stu-id="40819-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40819-116">备注</span><span class="sxs-lookup"><span data-stu-id="40819-116">Remarks</span></span>  
 <span data-ttu-id="40819-117">在成功完成，`pdwSize`参数设置为路径的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="40819-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40819-118">要求</span><span class="sxs-lookup"><span data-stu-id="40819-118">Requirements</span></span>  
 <span data-ttu-id="40819-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40819-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40819-120">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="40819-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="40819-121">**库：**为 Fusion.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="40819-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="40819-122">使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="40819-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="40819-123">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40819-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40819-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40819-124">See Also</span></span>  
 [<span data-ttu-id="40819-125">CreateHistoryReader 函数</span><span class="sxs-lookup"><span data-stu-id="40819-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="40819-126">NukeDownloadedCache 函数</span><span class="sxs-lookup"><span data-stu-id="40819-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="40819-127">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="40819-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
