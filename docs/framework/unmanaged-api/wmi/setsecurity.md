---
title: SetSecurity 函数 （非托管 API 参考）
description: SetSecurity 函数检索当前线程的模拟令牌。
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7200e3a19fcadabb5e149c38b620b3f60907c392
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948533"
---
# <a name="setsecurity-function"></a><span data-ttu-id="d35ff-103">SetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="d35ff-103">SetSecurity function</span></span>

<span data-ttu-id="d35ff-104">检索与当前线程关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="d35ff-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d35ff-105">语法</span><span class="sxs-lookup"><span data-stu-id="d35ff-105">Syntax</span></span>

```
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="d35ff-106">参数</span><span class="sxs-lookup"><span data-stu-id="d35ff-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="d35ff-107">[out]该函数返回时，包含一个指向`boolean`，该值指示令牌是否应通过调用重置[ResetSecurity](resetsecurity.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d35ff-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="d35ff-108">[out]当函数返回时，包含与当前线程关联的模拟令牌句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="d35ff-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="d35ff-109">其值可以是`null`是否存在任何与当前线程关联的令牌。</span><span class="sxs-lookup"><span data-stu-id="d35ff-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="d35ff-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d35ff-110">Return value</span></span>

<span data-ttu-id="d35ff-111">如果函数成功，返回值是`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="d35ff-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="d35ff-112">如果函数失败，返回值是一个非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="d35ff-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="d35ff-113">若要获得扩展错误信息，请调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d35ff-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="d35ff-114">要求</span><span class="sxs-lookup"><span data-stu-id="d35ff-114">Requirements</span></span>

 <span data-ttu-id="d35ff-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d35ff-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="d35ff-116">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d35ff-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="d35ff-117">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d35ff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d35ff-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d35ff-118">See also</span></span>

- [<span data-ttu-id="d35ff-119">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d35ff-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)