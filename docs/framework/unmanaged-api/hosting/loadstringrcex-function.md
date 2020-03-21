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
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177986"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="80792-102">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="80792-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="80792-103">将 HRESULT 值转换为指定区域性的相应错误消息。</span><span class="sxs-lookup"><span data-stu-id="80792-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="80792-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="80792-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80792-105">语法</span><span class="sxs-lookup"><span data-stu-id="80792-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80792-106">parameters</span><span class="sxs-lookup"><span data-stu-id="80792-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="80792-107">[在]区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="80792-107">[in] A culture identifier.</span></span> <span data-ttu-id="80792-108">通过 -1`lcid`用于使用默认区域性。</span><span class="sxs-lookup"><span data-stu-id="80792-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="80792-109">[在]A HRESULT。</span><span class="sxs-lookup"><span data-stu-id="80792-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="80792-110">[出]成功完成后包含错误消息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="80792-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="80792-111">[在]错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="80792-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="80792-112">[在]忽视。</span><span class="sxs-lookup"><span data-stu-id="80792-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="80792-113">[出]指向错误消息长度的指针。</span><span class="sxs-lookup"><span data-stu-id="80792-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80792-114">返回值</span><span class="sxs-lookup"><span data-stu-id="80792-114">Return Value</span></span>  
 <span data-ttu-id="80792-115">此方法返回 WinError.h 中定义的标准 COM 错误代码，以及以下值。</span><span class="sxs-lookup"><span data-stu-id="80792-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="80792-116">返回代码</span><span class="sxs-lookup"><span data-stu-id="80792-116">Return code</span></span>|<span data-ttu-id="80792-117">说明</span><span class="sxs-lookup"><span data-stu-id="80792-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="80792-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="80792-118">S_OK</span></span>|<span data-ttu-id="80792-119">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="80792-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="80792-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="80792-120">E_INVALIDARG</span></span>|<span data-ttu-id="80792-121">`szBuffer`为空或`iMax`为零 （0）。</span><span class="sxs-lookup"><span data-stu-id="80792-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80792-122">备注</span><span class="sxs-lookup"><span data-stu-id="80792-122">Remarks</span></span>  
 <span data-ttu-id="80792-123">如果方法未成功完成，`szBuffer`则包含一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="80792-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80792-124">要求</span><span class="sxs-lookup"><span data-stu-id="80792-124">Requirements</span></span>  
 <span data-ttu-id="80792-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="80792-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80792-126">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80792-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80792-127">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80792-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80792-128">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80792-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80792-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80792-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="80792-130">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="80792-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="80792-131">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="80792-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
