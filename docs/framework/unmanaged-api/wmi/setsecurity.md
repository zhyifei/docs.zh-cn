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
ms.openlocfilehash: 0fd354e1103832abee7f634eace3dd6defa8b646
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458746"
---
# <a name="setsecurity-function"></a><span data-ttu-id="a9624-103">SetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="a9624-103">SetSecurity function</span></span>
<span data-ttu-id="a9624-104">检索与当前线程关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="a9624-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a9624-105">语法</span><span class="sxs-lookup"><span data-stu-id="a9624-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="a9624-106">参数</span><span class="sxs-lookup"><span data-stu-id="a9624-106">Parameters</span></span>

<span data-ttu-id="a9624-107">`pNeedToReset` [out]当函数返回时，包含指向的`boolean`，该值指示令牌是否应该重置通过调用[ResetSecurity](resetsecurity.md)函数。</span><span class="sxs-lookup"><span data-stu-id="a9624-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="a9624-108">[out]当函数返回时，包含与当前线程关联的模拟令牌的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="a9624-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="a9624-109">其值可以是`null`是否没有与当前线程关联的标记。</span><span class="sxs-lookup"><span data-stu-id="a9624-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="a9624-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a9624-110">Return value</span></span>

<span data-ttu-id="a9624-111">如果函数成功，则返回值是`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="a9624-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="a9624-112">如果函数失败，返回值将为非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="a9624-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="a9624-113">若要获得扩展的错误信息，调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="a9624-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="a9624-114">要求</span><span class="sxs-lookup"><span data-stu-id="a9624-114">Requirements</span></span>  
 <span data-ttu-id="a9624-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9624-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9624-116">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a9624-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a9624-117">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a9624-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9624-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9624-118">See also</span></span>  
[<span data-ttu-id="a9624-119">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="a9624-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
