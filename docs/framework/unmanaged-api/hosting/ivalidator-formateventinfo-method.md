---
title: IValidator::FormatEventInfo 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 9b3a6bab8672f3ef3fca5f89c60b03a43477cce5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123296"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="c3bd9-102">IValidator::FormatEventInfo 方法</span><span class="sxs-lookup"><span data-stu-id="c3bd9-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="c3bd9-103">获取与指定的验证错误相对应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="c3bd9-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3bd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3bd9-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3bd9-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3bd9-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="c3bd9-106">中传递给验证错误处理程序的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="c3bd9-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="c3bd9-107">中一个 `VEContext` 实例，其中包含有关验证错误的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="c3bd9-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="c3bd9-108">[in，out]包含返回的错误消息的字符串。</span><span class="sxs-lookup"><span data-stu-id="c3bd9-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="c3bd9-109">中错误消息的最大长度。</span><span class="sxs-lookup"><span data-stu-id="c3bd9-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="c3bd9-110">中一个安全数组，其中包含描述错误的其他参数。</span><span class="sxs-lookup"><span data-stu-id="c3bd9-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3bd9-111">要求</span><span class="sxs-lookup"><span data-stu-id="c3bd9-111">Requirements</span></span>  
 <span data-ttu-id="c3bd9-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3bd9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3bd9-113">**标头：** IValidator，IValidator</span><span class="sxs-lookup"><span data-stu-id="c3bd9-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="c3bd9-114">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c3bd9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3bd9-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3bd9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
