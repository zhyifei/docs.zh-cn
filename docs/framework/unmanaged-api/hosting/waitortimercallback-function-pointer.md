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
ms.openlocfilehash: db6a20dee21b6c8bbd55fa9b52a159a00fe310d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092035"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="eef2c-102">WAITORTIMERCALLBACK 函数指针</span><span class="sxs-lookup"><span data-stu-id="eef2c-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="eef2c-103">指向一个函数，该函数通知宿主等待句柄（<xref:System.Threading.WaitHandle>）已发出信号或超时。</span><span class="sxs-lookup"><span data-stu-id="eef2c-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="eef2c-104">此函数指针在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="eef2c-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eef2c-105">语法</span><span class="sxs-lookup"><span data-stu-id="eef2c-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eef2c-106">参数</span><span class="sxs-lookup"><span data-stu-id="eef2c-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="eef2c-107">中指向对象的指针，该对象包含由宿主定义的信息。</span><span class="sxs-lookup"><span data-stu-id="eef2c-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="eef2c-108">[in] `true` 等待句柄超时，则为; 如果等待句柄已终止，则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="eef2c-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eef2c-109">备注</span><span class="sxs-lookup"><span data-stu-id="eef2c-109">Remarks</span></span>  
 <span data-ttu-id="eef2c-110">`WAITORTIMERCALLBACK` 点的函数是回调函数，并且必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="eef2c-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eef2c-111">要求</span><span class="sxs-lookup"><span data-stu-id="eef2c-111">Requirements</span></span>  
 <span data-ttu-id="eef2c-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eef2c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eef2c-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eef2c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eef2c-114">**库：** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="eef2c-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="eef2c-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eef2c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef2c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="eef2c-116">See also</span></span>

- [<span data-ttu-id="eef2c-117">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="eef2c-117">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
