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
ms.openlocfilehash: 68332aee895f012bcf6ab6a72936c8dddc7f28a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122036"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="1884f-102">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="1884f-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="1884f-103">将 HRESULT 值转换为指定区域性的适当错误消息。</span><span class="sxs-lookup"><span data-stu-id="1884f-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="1884f-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="1884f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1884f-105">语法</span><span class="sxs-lookup"><span data-stu-id="1884f-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1884f-106">参数</span><span class="sxs-lookup"><span data-stu-id="1884f-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="1884f-107">中区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="1884f-107">[in] A culture identifier.</span></span> <span data-ttu-id="1884f-108">传递-1，以便 `lcid` 使用默认区域性。</span><span class="sxs-lookup"><span data-stu-id="1884f-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="1884f-109">中HRESULT。</span><span class="sxs-lookup"><span data-stu-id="1884f-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="1884f-110">弄一个缓冲区，其中包含成功完成后的错误消息。</span><span class="sxs-lookup"><span data-stu-id="1884f-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="1884f-111">中错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="1884f-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="1884f-112">中掉.</span><span class="sxs-lookup"><span data-stu-id="1884f-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="1884f-113">弄指向错误消息长度的指针。</span><span class="sxs-lookup"><span data-stu-id="1884f-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1884f-114">返回值</span><span class="sxs-lookup"><span data-stu-id="1884f-114">Return Value</span></span>  
 <span data-ttu-id="1884f-115">除以下值外，此方法还返回 Winerror.h 中定义的标准 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="1884f-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="1884f-116">返回代码</span><span class="sxs-lookup"><span data-stu-id="1884f-116">Return code</span></span>|<span data-ttu-id="1884f-117">描述</span><span class="sxs-lookup"><span data-stu-id="1884f-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1884f-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1884f-118">S_OK</span></span>|<span data-ttu-id="1884f-119">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1884f-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="1884f-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1884f-120">E_INVALIDARG</span></span>|<span data-ttu-id="1884f-121">`szBuffer` 为 null 或 `iMax` 为零（0）。</span><span class="sxs-lookup"><span data-stu-id="1884f-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1884f-122">备注</span><span class="sxs-lookup"><span data-stu-id="1884f-122">Remarks</span></span>  
 <span data-ttu-id="1884f-123">如果该方法未成功完成，`szBuffer` 将包含空字符串。</span><span class="sxs-lookup"><span data-stu-id="1884f-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1884f-124">要求</span><span class="sxs-lookup"><span data-stu-id="1884f-124">Requirements</span></span>  
 <span data-ttu-id="1884f-125">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1884f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1884f-126">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1884f-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1884f-127">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1884f-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1884f-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1884f-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1884f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="1884f-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1884f-130">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="1884f-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="1884f-131">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="1884f-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
