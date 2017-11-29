---
title: "LoadStringRCEx 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadStringRCEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: LoadStringRCEx
helpviewer_keywords: LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3467ebcd0b821c2313f3535c5b594ef664546e4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="5466c-102">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="5466c-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="5466c-103">将转换为相应的错误消息为指定的区域性的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="5466c-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="5466c-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5466c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5466c-105">语法</span><span class="sxs-lookup"><span data-stu-id="5466c-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5466c-106">参数</span><span class="sxs-lookup"><span data-stu-id="5466c-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="5466c-107">[in]区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="5466c-107">[in] A culture identifier.</span></span> <span data-ttu-id="5466c-108">传递-1 `lcid` ，使用默认区域性。</span><span class="sxs-lookup"><span data-stu-id="5466c-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="5466c-109">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="5466c-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="5466c-110">[out]包含成功完成后的错误消息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5466c-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="5466c-111">[in]错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="5466c-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="5466c-112">[in]忽略。</span><span class="sxs-lookup"><span data-stu-id="5466c-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="5466c-113">[out]指向错误消息的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="5466c-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5466c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="5466c-114">Return Value</span></span>  
 <span data-ttu-id="5466c-115">此方法返回标准的 COM 错误代码，除了以下值中 WinError.h，定义。</span><span class="sxs-lookup"><span data-stu-id="5466c-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="5466c-116">返回代码</span><span class="sxs-lookup"><span data-stu-id="5466c-116">Return code</span></span>|<span data-ttu-id="5466c-117">描述</span><span class="sxs-lookup"><span data-stu-id="5466c-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5466c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="5466c-118">S_OK</span></span>|<span data-ttu-id="5466c-119">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="5466c-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="5466c-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5466c-120">E_INVALIDARG</span></span>|<span data-ttu-id="5466c-121">`szBuffer`为 null，或`iMax`为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="5466c-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5466c-122">备注</span><span class="sxs-lookup"><span data-stu-id="5466c-122">Remarks</span></span>  
 <span data-ttu-id="5466c-123">如果方法不成功，完成`szBuffer`包含一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="5466c-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5466c-124">要求</span><span class="sxs-lookup"><span data-stu-id="5466c-124">Requirements</span></span>  
 <span data-ttu-id="5466c-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5466c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5466c-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5466c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5466c-127">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5466c-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5466c-128">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5466c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5466c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5466c-129">See Also</span></span>  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="5466c-130">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="5466c-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [<span data-ttu-id="5466c-131">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="5466c-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
