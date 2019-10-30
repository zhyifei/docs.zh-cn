---
title: LPTHREAD_START_ROUTINE 函数指针
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
ms.openlocfilehash: c6e0c02af93b9df726202f397bbb2afc306f3b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090879"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="b7dce-102">LPTHREAD_START_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="b7dce-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="b7dce-103">指向一个函数，该函数通知宿主线程已开始执行。</span><span class="sxs-lookup"><span data-stu-id="b7dce-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="b7dce-104">此函数指针在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="b7dce-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7dce-105">语法</span><span class="sxs-lookup"><span data-stu-id="b7dce-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7dce-106">参数</span><span class="sxs-lookup"><span data-stu-id="b7dce-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="b7dce-107">中指向已开始执行的代码的指针。</span><span class="sxs-lookup"><span data-stu-id="b7dce-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7dce-108">备注</span><span class="sxs-lookup"><span data-stu-id="b7dce-108">Remarks</span></span>  
 <span data-ttu-id="b7dce-109">`LPTHREAD_START_ROUTINE` 点的函数是回调函数，并且必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="b7dce-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7dce-110">要求</span><span class="sxs-lookup"><span data-stu-id="b7dce-110">Requirements</span></span>  
 <span data-ttu-id="b7dce-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7dce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7dce-112">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b7dce-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7dce-113">**库：** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="b7dce-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b7dce-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7dce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7dce-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7dce-115">See also</span></span>

- [<span data-ttu-id="b7dce-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="b7dce-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
