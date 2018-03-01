---
title: "IValidator::FormatEventInfo 方法"
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
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ddff0a640f37133bf5a44aea1e371d73d0fd2856
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="5bcff-102">IValidator::FormatEventInfo 方法</span><span class="sxs-lookup"><span data-stu-id="5bcff-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="5bcff-103">获取对应于指定的验证错误的错误消息。</span><span class="sxs-lookup"><span data-stu-id="5bcff-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcff-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bcff-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bcff-105">参数</span><span class="sxs-lookup"><span data-stu-id="5bcff-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="5bcff-106">[in]HRESULT 值传递到验证错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="5bcff-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="5bcff-107">[in]A`VEContext`实例，其中包含有关验证错误的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="5bcff-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="5bcff-108">[在中，out]包含返回的错误消息的字符串。</span><span class="sxs-lookup"><span data-stu-id="5bcff-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="5bcff-109">[in]错误消息的最大长度。</span><span class="sxs-lookup"><span data-stu-id="5bcff-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="5bcff-110">[in]包含描述错误的其他参数的安全数组。</span><span class="sxs-lookup"><span data-stu-id="5bcff-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bcff-111">惠?</span><span class="sxs-lookup"><span data-stu-id="5bcff-111">Requirements</span></span>  
 <span data-ttu-id="5bcff-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bcff-113">**标头：** IValidator.idl、 IValidator.h</span><span class="sxs-lookup"><span data-stu-id="5bcff-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="5bcff-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5bcff-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bcff-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bcff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bcff-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bcff-116">See Also</span></span>  
 
