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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 463bcf451574700d02f933d024ea5c24cedd259d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="loadstringrc-function"></a><span data-ttu-id="59a8c-102">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="59a8c-102">LoadStringRC Function</span></span>
<span data-ttu-id="59a8c-103">将 HRESULT 值转换为一条错误消息中，通过使用当前线程的默认区域性。</span><span class="sxs-lookup"><span data-stu-id="59a8c-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="59a8c-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="59a8c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59a8c-105">语法</span><span class="sxs-lookup"><span data-stu-id="59a8c-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59a8c-106">参数</span><span class="sxs-lookup"><span data-stu-id="59a8c-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="59a8c-107">[in]HRESULT。</span><span class="sxs-lookup"><span data-stu-id="59a8c-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="59a8c-108">[out]包含成功完成后的错误消息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="59a8c-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="59a8c-109">[in]错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="59a8c-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="59a8c-110">[in]忽略。</span><span class="sxs-lookup"><span data-stu-id="59a8c-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59a8c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="59a8c-111">Return Value</span></span>  
 <span data-ttu-id="59a8c-112">此方法返回标准的组件对象模型 (COM) 错误代码，除了以下值中 WinError.h，定义。</span><span class="sxs-lookup"><span data-stu-id="59a8c-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="59a8c-113">返回代码</span><span class="sxs-lookup"><span data-stu-id="59a8c-113">Return code</span></span>|<span data-ttu-id="59a8c-114">描述</span><span class="sxs-lookup"><span data-stu-id="59a8c-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="59a8c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="59a8c-115">S_OK</span></span>|<span data-ttu-id="59a8c-116">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="59a8c-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="59a8c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="59a8c-117">E_INVALIDARG</span></span>|<span data-ttu-id="59a8c-118">`szBuffer` 为 null 或`iMax`为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="59a8c-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59a8c-119">备注</span><span class="sxs-lookup"><span data-stu-id="59a8c-119">Remarks</span></span>  
 <span data-ttu-id="59a8c-120">如果方法不成功，完成`szBuffer`包含一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="59a8c-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59a8c-121">要求</span><span class="sxs-lookup"><span data-stu-id="59a8c-121">Requirements</span></span>  
 <span data-ttu-id="59a8c-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="59a8c-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59a8c-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="59a8c-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59a8c-124">**库：** MSCorEE.dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="59a8c-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="59a8c-125">使用而不是 Mscorwks.dll MSCorEE.dll 来确保面向.NET Framework 的正确版本。</span><span class="sxs-lookup"><span data-stu-id="59a8c-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="59a8c-126">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59a8c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a8c-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="59a8c-127">See Also</span></span>  
 [<span data-ttu-id="59a8c-128">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="59a8c-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 [<span data-ttu-id="59a8c-129">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="59a8c-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
