---
title: 重置安全功能（非托管 API 引用）
description: 重置安全功能将模拟令牌分配给当前线程。
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: ce74494455c6cc7fe382a4ea4ef2ff0c4e98c61b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174857"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="58528-103">ResetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="58528-103">ResetSecurity function</span></span>
<span data-ttu-id="58528-104">将提供的模拟令牌分配给当前线程。</span><span class="sxs-lookup"><span data-stu-id="58528-104">Assigns the supplied impersonation token to the current thread.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="58528-105">语法</span><span class="sxs-lookup"><span data-stu-id="58528-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a><span data-ttu-id="58528-106">parameters</span><span class="sxs-lookup"><span data-stu-id="58528-106">Parameters</span></span>

`token`  
<span data-ttu-id="58528-107">[在]要与当前线程关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="58528-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="58528-108">其值可为 `null`。</span><span class="sxs-lookup"><span data-stu-id="58528-108">Its value can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="58528-109">返回值</span><span class="sxs-lookup"><span data-stu-id="58528-109">Return value</span></span>

<span data-ttu-id="58528-110">如果函数成功，则返回值为`S_OK`（0）。</span><span class="sxs-lookup"><span data-stu-id="58528-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="58528-111">如果函数失败，返回值是非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="58528-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="58528-112">要获取扩展的错误信息，请致电[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="58528-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="58528-113">要求</span><span class="sxs-lookup"><span data-stu-id="58528-113">Requirements</span></span>  
 <span data-ttu-id="58528-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58528-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58528-115">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="58528-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="58528-116">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="58528-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58528-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58528-117">See also</span></span>

- [<span data-ttu-id="58528-118">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="58528-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
