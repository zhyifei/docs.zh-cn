---
title: GetErrorInfo 函数 （非托管 API 参考）
description: GetErrorInfo 函数从上一个函数调用中检索错误信息。
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef52a4e503597e08eae407571f02bf63adafc4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455950"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="b931f-103">GetErrorInfo 函数</span><span class="sxs-lookup"><span data-stu-id="b931f-103">GetErrorInfo function</span></span>
<span data-ttu-id="b931f-104">从以前的函数调用中检索错误信息。</span><span class="sxs-lookup"><span data-stu-id="b931f-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b931f-105">语法</span><span class="sxs-lookup"><span data-stu-id="b931f-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="b931f-106">返回值</span><span class="sxs-lookup"><span data-stu-id="b931f-106">Return value</span></span>

<span data-ttu-id="b931f-107">指向[IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx)对象，如果函数调用成功，或`null`如果失败。</span><span class="sxs-lookup"><span data-stu-id="b931f-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b931f-108">备注</span><span class="sxs-lookup"><span data-stu-id="b931f-108">Remarks</span></span>

<span data-ttu-id="b931f-109">此函数包装对的调用[IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="b931f-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b931f-110">要求</span><span class="sxs-lookup"><span data-stu-id="b931f-110">Requirements</span></span>  
 <span data-ttu-id="b931f-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b931f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b931f-112">**标头：** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="b931f-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="b931f-113">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b931f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b931f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b931f-114">See also</span></span>  
[<span data-ttu-id="b931f-115">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="b931f-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
