---
title: LoadStringRCEx 函数
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c3185bdc0776d6536458ce03c348ed77b8ba0b9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499090"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="14676-102">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="14676-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="14676-103">将转换为相应的错误消息为指定的区域性的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="14676-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="14676-104">此函数中不推荐[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="14676-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14676-105">语法</span><span class="sxs-lookup"><span data-stu-id="14676-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="14676-106">参数</span><span class="sxs-lookup"><span data-stu-id="14676-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="14676-107">[in]区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="14676-107">[in] A culture identifier.</span></span> <span data-ttu-id="14676-108">传递-1`lcid`若要使用默认区域性。</span><span class="sxs-lookup"><span data-stu-id="14676-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="14676-109">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="14676-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="14676-110">[out]包含成功完成后的错误消息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="14676-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="14676-111">[in]错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="14676-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="14676-112">[in]忽略。</span><span class="sxs-lookup"><span data-stu-id="14676-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="14676-113">[out]指向错误消息的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="14676-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14676-114">返回值</span><span class="sxs-lookup"><span data-stu-id="14676-114">Return Value</span></span>  
 <span data-ttu-id="14676-115">此方法返回标准 COM 错误代码，定义在 WinError.h，除了以下值。</span><span class="sxs-lookup"><span data-stu-id="14676-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="14676-116">返回代码</span><span class="sxs-lookup"><span data-stu-id="14676-116">Return code</span></span>|<span data-ttu-id="14676-117">描述</span><span class="sxs-lookup"><span data-stu-id="14676-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="14676-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="14676-118">S_OK</span></span>|<span data-ttu-id="14676-119">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="14676-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="14676-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="14676-120">E_INVALIDARG</span></span>|<span data-ttu-id="14676-121">`szBuffer` 为 null，或`iMax`为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="14676-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14676-122">备注</span><span class="sxs-lookup"><span data-stu-id="14676-122">Remarks</span></span>  
 <span data-ttu-id="14676-123">如果该方法不成功，完成`szBuffer`包含空字符串。</span><span class="sxs-lookup"><span data-stu-id="14676-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14676-124">要求</span><span class="sxs-lookup"><span data-stu-id="14676-124">Requirements</span></span>  
 <span data-ttu-id="14676-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14676-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14676-126">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14676-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14676-127">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="14676-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14676-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14676-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14676-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="14676-129">See also</span></span>
- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="14676-130">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="14676-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="14676-131">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="14676-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
