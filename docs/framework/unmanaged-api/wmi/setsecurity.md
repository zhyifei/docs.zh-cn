---
title: SetSecurity 函数（非托管 API 参考）
description: SetSecurity 函数检索当前线程的模拟标记。
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
ms.openlocfilehash: 94c76213acb66116105d181e9961a33976047ee7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798249"
---
# <a name="setsecurity-function"></a><span data-ttu-id="6d507-103">SetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="6d507-103">SetSecurity function</span></span>

<span data-ttu-id="6d507-104">检索与当前线程关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="6d507-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6d507-105">语法</span><span class="sxs-lookup"><span data-stu-id="6d507-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="6d507-106">参数</span><span class="sxs-lookup"><span data-stu-id="6d507-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="6d507-107">弄当函数返回时，将包含一个指向`boolean`的指针，该指针指示是否应通过调用[ResetSecurity](resetsecurity.md)函数来重置令牌。</span><span class="sxs-lookup"><span data-stu-id="6d507-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="6d507-108">弄当函数返回时，包含指向与当前线程关联的模拟标记的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="6d507-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="6d507-109">如果没有与当前`null`线程关联的标记，则其值可以为。</span><span class="sxs-lookup"><span data-stu-id="6d507-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="6d507-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6d507-110">Return value</span></span>

<span data-ttu-id="6d507-111">如果该函数成功，则返回值为`S_OK` （0）。</span><span class="sxs-lookup"><span data-stu-id="6d507-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="6d507-112">如果函数失败，则返回值为非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="6d507-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="6d507-113">若要获取扩展的错误信息，请调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6d507-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="6d507-114">要求</span><span class="sxs-lookup"><span data-stu-id="6d507-114">Requirements</span></span>

 <span data-ttu-id="6d507-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d507-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="6d507-116">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6d507-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="6d507-117">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6d507-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6d507-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d507-118">See also</span></span>

- [<span data-ttu-id="6d507-119">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="6d507-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
