---
title: _EFN_GetManagedExcepStack 函数
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e201b9a350c030da59e2b6ed27f84f570c8e621
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126654"
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="affb6-102">_EFN_GetManagedExcepStack 函数</span><span class="sxs-lookup"><span data-stu-id="affb6-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="affb6-103">给定托管的异常对象地址后，将返回其中包含的堆栈跟踪的字符串版本。</span><span class="sxs-lookup"><span data-stu-id="affb6-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="affb6-104">语法</span><span class="sxs-lookup"><span data-stu-id="affb6-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="affb6-105">参数</span><span class="sxs-lookup"><span data-stu-id="affb6-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="affb6-106">[in]正在调试客户端。</span><span class="sxs-lookup"><span data-stu-id="affb6-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="affb6-107">[in]托管的对象指针，派生自<xref:System.Exception>。</span><span class="sxs-lookup"><span data-stu-id="affb6-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="affb6-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="affb6-108">szStackString</span></span>  
 <span data-ttu-id="affb6-109">[out]返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="affb6-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="affb6-110">[out]字符串缓冲区中有可用的字符数。</span><span class="sxs-lookup"><span data-stu-id="affb6-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="affb6-111">备注</span><span class="sxs-lookup"><span data-stu-id="affb6-111">Remarks</span></span>  
 <span data-ttu-id="affb6-112">如果没有任何托管的代码的线程上当前上下文中，该函数返回 HRESULT SOS_E_NOMANAGEDCODE 0xa0 设施值和错误代码为 0x1000。</span><span class="sxs-lookup"><span data-stu-id="affb6-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="affb6-113">要求</span><span class="sxs-lookup"><span data-stu-id="affb6-113">Requirements</span></span>  
 <span data-ttu-id="affb6-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="affb6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="affb6-115">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="affb6-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="affb6-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="affb6-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="affb6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="affb6-117">See also</span></span>

- [<span data-ttu-id="affb6-118">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="affb6-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
