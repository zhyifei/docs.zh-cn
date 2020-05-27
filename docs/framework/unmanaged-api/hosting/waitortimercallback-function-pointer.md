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
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009440"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="bd38d-102">WAITORTIMERCALLBACK 函数指针</span><span class="sxs-lookup"><span data-stu-id="bd38d-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="bd38d-103">指向一个函数，该函数通知宿主等待句柄（ <xref:System.Threading.WaitHandle> ）已发出信号或超时。</span><span class="sxs-lookup"><span data-stu-id="bd38d-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="bd38d-104">此函数指针在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="bd38d-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd38d-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd38d-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd38d-106">参数</span><span class="sxs-lookup"><span data-stu-id="bd38d-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="bd38d-107">中指向对象的指针，该对象包含由宿主定义的信息。</span><span class="sxs-lookup"><span data-stu-id="bd38d-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="bd38d-108">[in] `true`如果等待句柄超时，则为; 如果等待句柄已终止，则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="bd38d-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd38d-109">备注</span><span class="sxs-lookup"><span data-stu-id="bd38d-109">Remarks</span></span>  
 <span data-ttu-id="bd38d-110">指向该函数的 `WAITORTIMERCALLBACK` 点是回调函数，并且必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="bd38d-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd38d-111">要求</span><span class="sxs-lookup"><span data-stu-id="bd38d-111">Requirements</span></span>  
 <span data-ttu-id="bd38d-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bd38d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd38d-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="bd38d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd38d-114">**库：** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="bd38d-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="bd38d-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd38d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd38d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd38d-116">See also</span></span>

- [<span data-ttu-id="bd38d-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="bd38d-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
