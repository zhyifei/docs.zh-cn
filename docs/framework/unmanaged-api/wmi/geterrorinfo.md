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
ms.openlocfilehash: 5f25777402fa31e72cbbf36f58a6c4cc65542979
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44039470"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="e886e-103">GetErrorInfo 函数</span><span class="sxs-lookup"><span data-stu-id="e886e-103">GetErrorInfo function</span></span>
<span data-ttu-id="e886e-104">从上一个函数调用中检索错误信息。</span><span class="sxs-lookup"><span data-stu-id="e886e-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e886e-105">语法</span><span class="sxs-lookup"><span data-stu-id="e886e-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="e886e-106">返回值</span><span class="sxs-lookup"><span data-stu-id="e886e-106">Return value</span></span>

<span data-ttu-id="e886e-107">指向的指针[IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)对象，如果函数调用成功，或`null`失败。</span><span class="sxs-lookup"><span data-stu-id="e886e-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e886e-108">备注</span><span class="sxs-lookup"><span data-stu-id="e886e-108">Remarks</span></span>

<span data-ttu-id="e886e-109">此函数包装对的调用[IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)方法。</span><span class="sxs-lookup"><span data-stu-id="e886e-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e886e-110">要求</span><span class="sxs-lookup"><span data-stu-id="e886e-110">Requirements</span></span>  
 <span data-ttu-id="e886e-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e886e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e886e-112">**标头：** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="e886e-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="e886e-113">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e886e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e886e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e886e-114">See also</span></span>  
[<span data-ttu-id="e886e-115">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e886e-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
