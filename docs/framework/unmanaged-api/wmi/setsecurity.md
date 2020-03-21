---
title: 设置安全功能（非托管 API 引用）
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
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176729"
---
# <a name="setsecurity-function"></a><span data-ttu-id="15f50-103">SetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="15f50-103">SetSecurity function</span></span>

<span data-ttu-id="15f50-104">检索与当前线程关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="15f50-104">Retrieves the impersonation token associated with the current thread.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="15f50-105">语法</span><span class="sxs-lookup"><span data-stu-id="15f50-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a><span data-ttu-id="15f50-106">parameters</span><span class="sxs-lookup"><span data-stu-id="15f50-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="15f50-107">[出]当函数返回时，包含指向 的`boolean`指针，指示是否应通过调用[ResetSecurity](resetsecurity.md)函数重置令牌。</span><span class="sxs-lookup"><span data-stu-id="15f50-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="15f50-108">[出]当函数返回时，包含指向与当前线程关联的模拟令牌句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="15f50-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="15f50-109">如果没有与当前线程`null`关联的令牌，则其值可以是。</span><span class="sxs-lookup"><span data-stu-id="15f50-109">Its value can be `null` if there is no token associated with the current thread.</span></span>

## <a name="return-value"></a><span data-ttu-id="15f50-110">返回值</span><span class="sxs-lookup"><span data-stu-id="15f50-110">Return value</span></span>

<span data-ttu-id="15f50-111">如果函数成功，则返回值为`S_OK`（0）。</span><span class="sxs-lookup"><span data-stu-id="15f50-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="15f50-112">如果函数失败，返回值是非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="15f50-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="15f50-113">要获取扩展的错误信息，请致电[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="15f50-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="15f50-114">要求</span><span class="sxs-lookup"><span data-stu-id="15f50-114">Requirements</span></span>

 <span data-ttu-id="15f50-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15f50-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="15f50-116">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="15f50-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="15f50-117">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15f50-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="15f50-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15f50-118">See also</span></span>

- [<span data-ttu-id="15f50-119">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="15f50-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
