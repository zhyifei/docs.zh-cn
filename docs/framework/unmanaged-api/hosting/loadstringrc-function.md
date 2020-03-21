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
ms.openlocfilehash: 56ae7b7cf3b577bfe41ebd0bdd98e0da68047b44
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176235"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="34e6f-102">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="34e6f-102">LoadStringRC Function</span></span>
<span data-ttu-id="34e6f-103">使用当前线程的默认区域性将 HRESULT 值转换为错误消息。</span><span class="sxs-lookup"><span data-stu-id="34e6f-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="34e6f-104">此功能已在 .NET 框架 4 中弃用。</span><span class="sxs-lookup"><span data-stu-id="34e6f-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e6f-105">语法</span><span class="sxs-lookup"><span data-stu-id="34e6f-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34e6f-106">parameters</span><span class="sxs-lookup"><span data-stu-id="34e6f-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="34e6f-107">[在]A HRESULT。</span><span class="sxs-lookup"><span data-stu-id="34e6f-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="34e6f-108">[出]成功完成后包含错误消息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="34e6f-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="34e6f-109">[在]错误消息缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="34e6f-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="34e6f-110">[在]忽视。</span><span class="sxs-lookup"><span data-stu-id="34e6f-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34e6f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="34e6f-111">Return Value</span></span>  
 <span data-ttu-id="34e6f-112">此方法返回 WinError.h 中定义的标准组件对象模型 （COM） 错误代码，以及以下值。</span><span class="sxs-lookup"><span data-stu-id="34e6f-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="34e6f-113">返回代码</span><span class="sxs-lookup"><span data-stu-id="34e6f-113">Return code</span></span>|<span data-ttu-id="34e6f-114">说明</span><span class="sxs-lookup"><span data-stu-id="34e6f-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="34e6f-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="34e6f-115">S_OK</span></span>|<span data-ttu-id="34e6f-116">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="34e6f-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="34e6f-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="34e6f-117">E_INVALIDARG</span></span>|<span data-ttu-id="34e6f-118">`szBuffer`为空或`iMax`为零 （0）。</span><span class="sxs-lookup"><span data-stu-id="34e6f-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34e6f-119">备注</span><span class="sxs-lookup"><span data-stu-id="34e6f-119">Remarks</span></span>  
 <span data-ttu-id="34e6f-120">如果方法未成功完成，`szBuffer`则包含一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="34e6f-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34e6f-121">要求</span><span class="sxs-lookup"><span data-stu-id="34e6f-121">Requirements</span></span>  
 <span data-ttu-id="34e6f-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34e6f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34e6f-123">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="34e6f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34e6f-124">**库：** MSCorE.dll 和 Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="34e6f-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="34e6f-125">使用 MSCorEE.dll 而不是 mscorwks.dll 来确保针对 .NET 框架的正确版本。</span><span class="sxs-lookup"><span data-stu-id="34e6f-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="34e6f-126">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34e6f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e6f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34e6f-127">See also</span></span>

- [<span data-ttu-id="34e6f-128">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="34e6f-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="34e6f-129">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="34e6f-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
