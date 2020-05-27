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
ms.openlocfilehash: a05cbe985c2cfebb67756fdfb54398b36e87f441
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008503"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="fbfe7-102">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="fbfe7-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="fbfe7-103">将 HRESULT 值转换为指定区域性的适当错误消息。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="fbfe7-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbfe7-105">语法</span><span class="sxs-lookup"><span data-stu-id="fbfe7-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fbfe7-106">参数</span><span class="sxs-lookup"><span data-stu-id="fbfe7-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="fbfe7-107">中区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-107">[in] A culture identifier.</span></span> <span data-ttu-id="fbfe7-108">为传递-1 `lcid` 以使用默认区域性。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="fbfe7-109">中HRESULT。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="fbfe7-110">弄一个缓冲区，其中包含成功完成后的错误消息。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="fbfe7-111">中错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="fbfe7-112">中掉.</span><span class="sxs-lookup"><span data-stu-id="fbfe7-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="fbfe7-113">弄指向错误消息长度的指针。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbfe7-114">返回值</span><span class="sxs-lookup"><span data-stu-id="fbfe7-114">Return Value</span></span>  
 <span data-ttu-id="fbfe7-115">除以下值外，此方法还返回 Winerror.h 中定义的标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="fbfe7-116">返回代码</span><span class="sxs-lookup"><span data-stu-id="fbfe7-116">Return code</span></span>|<span data-ttu-id="fbfe7-117">说明</span><span class="sxs-lookup"><span data-stu-id="fbfe7-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="fbfe7-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbfe7-118">S_OK</span></span>|<span data-ttu-id="fbfe7-119">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="fbfe7-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fbfe7-120">E_INVALIDARG</span></span>|<span data-ttu-id="fbfe7-121">`szBuffer`为 null，或者 `iMax` 为零（0）。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbfe7-122">备注</span><span class="sxs-lookup"><span data-stu-id="fbfe7-122">Remarks</span></span>  
 <span data-ttu-id="fbfe7-123">如果该方法未成功完成，则 `szBuffer` 包含一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbfe7-124">要求</span><span class="sxs-lookup"><span data-stu-id="fbfe7-124">Requirements</span></span>  
 <span data-ttu-id="fbfe7-125">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fbfe7-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbfe7-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fbfe7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbfe7-127">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fbfe7-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbfe7-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbfe7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbfe7-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbfe7-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fbfe7-130">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="fbfe7-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="fbfe7-131">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="fbfe7-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
