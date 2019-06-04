---
title: WAITORTIMERCALLBACK 函数指针
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f938c7dcf08654eef1e2403426eb5c54d6d2a6b3
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490122"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="7f051-102">WAITORTIMERCALLBACK 函数指针</span><span class="sxs-lookup"><span data-stu-id="7f051-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="7f051-103">指向通知主机等待句柄的函数 (<xref:System.Threading.WaitHandle>) 已发出信号或操作已超时。</span><span class="sxs-lookup"><span data-stu-id="7f051-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="7f051-104">.NET Framework 4 中已弃用此函数指针。</span><span class="sxs-lookup"><span data-stu-id="7f051-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f051-105">语法</span><span class="sxs-lookup"><span data-stu-id="7f051-105">Syntax</span></span>  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f051-106">参数</span><span class="sxs-lookup"><span data-stu-id="7f051-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="7f051-107">[in]指向包含由主机定义的信息的对象的指针。</span><span class="sxs-lookup"><span data-stu-id="7f051-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="7f051-108">[in]`true`如果等待句柄已超时，或`false`如果其终止。</span><span class="sxs-lookup"><span data-stu-id="7f051-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f051-109">备注</span><span class="sxs-lookup"><span data-stu-id="7f051-109">Remarks</span></span>  
 <span data-ttu-id="7f051-110">该函数`WAITORTIMERCALLBACK`点是回调函数，必须由主机应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="7f051-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f051-111">要求</span><span class="sxs-lookup"><span data-stu-id="7f051-111">Requirements</span></span>  
 <span data-ttu-id="7f051-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f051-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f051-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7f051-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f051-114">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="7f051-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="7f051-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f051-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f051-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f051-116">See also</span></span>

- [<span data-ttu-id="7f051-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="7f051-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
