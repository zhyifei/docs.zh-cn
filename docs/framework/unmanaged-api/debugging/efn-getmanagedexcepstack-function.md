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
ms.openlocfilehash: 9bcc03cc97a62b4c1cadacd7c0b2bc46b9fec470
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134131"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="34562-102">\_EFN\_GetManagedExcepStack 函数</span><span class="sxs-lookup"><span data-stu-id="34562-102">\_EFN\_GetManagedExcepStack Function</span></span>
<span data-ttu-id="34562-103">给定托管的异常对象地址后，将返回其中包含的堆栈跟踪的字符串版本。</span><span class="sxs-lookup"><span data-stu-id="34562-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34562-104">语法</span><span class="sxs-lookup"><span data-stu-id="34562-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34562-105">参数</span><span class="sxs-lookup"><span data-stu-id="34562-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="34562-106">中正在调试的客户端。</span><span class="sxs-lookup"><span data-stu-id="34562-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="34562-107">中派生自 <xref:System.Exception>的托管对象指针。</span><span class="sxs-lookup"><span data-stu-id="34562-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="34562-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="34562-108">szStackString</span></span>  
 <span data-ttu-id="34562-109">弄返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="34562-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="34562-110">弄字符串缓冲区中的可用字符数。</span><span class="sxs-lookup"><span data-stu-id="34562-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34562-111">备注</span><span class="sxs-lookup"><span data-stu-id="34562-111">Remarks</span></span>  
 <span data-ttu-id="34562-112">如果当前在上下文中的线程上没有托管代码，则该函数将返回 HRESULT SOS_E_NOMANAGEDCODE，其设施值为0xa0，错误代码为0x1000。</span><span class="sxs-lookup"><span data-stu-id="34562-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34562-113">要求</span><span class="sxs-lookup"><span data-stu-id="34562-113">Requirements</span></span>  
 <span data-ttu-id="34562-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34562-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34562-115">**标头：** SOS_Stacktrace</span><span class="sxs-lookup"><span data-stu-id="34562-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="34562-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34562-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34562-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="34562-117">See also</span></span>

- [<span data-ttu-id="34562-118">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="34562-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
