---
title: LoadStringRC 函数
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 8bd0292ddf22453f8892ed8bddd10c2144877097
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008506"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="b379e-102">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="b379e-102">LoadStringRC Function</span></span>
<span data-ttu-id="b379e-103">使用当前线程的默认区域性将 HRESULT 值转换为错误消息。</span><span class="sxs-lookup"><span data-stu-id="b379e-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="b379e-104">此函数已在 .NET Framework 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="b379e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b379e-105">语法</span><span class="sxs-lookup"><span data-stu-id="b379e-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b379e-106">参数</span><span class="sxs-lookup"><span data-stu-id="b379e-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="b379e-107">中HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b379e-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="b379e-108">弄一个缓冲区，其中包含成功完成后的错误消息。</span><span class="sxs-lookup"><span data-stu-id="b379e-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="b379e-109">中错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="b379e-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="b379e-110">中掉.</span><span class="sxs-lookup"><span data-stu-id="b379e-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b379e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b379e-111">Return Value</span></span>  
 <span data-ttu-id="b379e-112">除以下值外，此方法还返回 Winerror.h 中定义的标准组件对象模型（COM）错误代码。</span><span class="sxs-lookup"><span data-stu-id="b379e-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="b379e-113">返回代码</span><span class="sxs-lookup"><span data-stu-id="b379e-113">Return code</span></span>|<span data-ttu-id="b379e-114">说明</span><span class="sxs-lookup"><span data-stu-id="b379e-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b379e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b379e-115">S_OK</span></span>|<span data-ttu-id="b379e-116">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="b379e-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="b379e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b379e-117">E_INVALIDARG</span></span>|<span data-ttu-id="b379e-118">`szBuffer`为 null 或 `iMax` 为零（0）。</span><span class="sxs-lookup"><span data-stu-id="b379e-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b379e-119">备注</span><span class="sxs-lookup"><span data-stu-id="b379e-119">Remarks</span></span>  
 <span data-ttu-id="b379e-120">如果该方法未成功完成，则 `szBuffer` 包含一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="b379e-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b379e-121">要求</span><span class="sxs-lookup"><span data-stu-id="b379e-121">Requirements</span></span>  
 <span data-ttu-id="b379e-122">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b379e-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b379e-123">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b379e-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b379e-124">**库：** Mscoree.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="b379e-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="b379e-125">使用 Mscoree.dll 而不是 Mscorwks.dll 来确保目标为正确的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="b379e-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b379e-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b379e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b379e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b379e-127">See also</span></span>

- [<span data-ttu-id="b379e-128">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="b379e-128">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)
- [<span data-ttu-id="b379e-129">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="b379e-129">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
