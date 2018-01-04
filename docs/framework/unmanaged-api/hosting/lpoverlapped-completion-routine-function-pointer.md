---
title: "LPOVERLAPPED_COMPLETION_ROUTINE 函数指针"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPOVERLAPPED_COMPLETION_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords: LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b1846cf8fff5c41fc54ddeec5b495b50c63581c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="f21f3-102">LPOVERLAPPED_COMPLETION_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="f21f3-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="f21f3-103">指向通知时的重叠的宿主的函数 (即异步) 对设备 i/o 操作已完成。</span><span class="sxs-lookup"><span data-stu-id="f21f3-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="f21f3-104">中已弃用此函数指针[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f21f3-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f21f3-105">语法</span><span class="sxs-lookup"><span data-stu-id="f21f3-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f21f3-106">参数</span><span class="sxs-lookup"><span data-stu-id="f21f3-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="f21f3-107">[in]一个值，如果设备已关闭; 是一个错误代码否则，此值为零。</span><span class="sxs-lookup"><span data-stu-id="f21f3-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="f21f3-108">关闭设备，则会立即完成所有挂起的设备 I/O。</span><span class="sxs-lookup"><span data-stu-id="f21f3-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="f21f3-109">[in]传输字节的 I/O 操作的数。</span><span class="sxs-lookup"><span data-stu-id="f21f3-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="f21f3-110">[in]指向包含要使用完成 I/O 请求信息的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="f21f3-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f21f3-111">备注</span><span class="sxs-lookup"><span data-stu-id="f21f3-111">Remarks</span></span>  
 <span data-ttu-id="f21f3-112">到函数`LPOVERLAPPED_COMPLETION_ROUTINE`点是一个回调函数，必须在承载应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="f21f3-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="f21f3-113">回调函数允许宿主处理已完成的 I/O 请求。</span><span class="sxs-lookup"><span data-stu-id="f21f3-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f21f3-114">惠?</span><span class="sxs-lookup"><span data-stu-id="f21f3-114">Requirements</span></span>  
 <span data-ttu-id="f21f3-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f21f3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f21f3-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f21f3-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f21f3-117">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="f21f3-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f21f3-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f21f3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21f3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f21f3-119">See Also</span></span>  
 [<span data-ttu-id="f21f3-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="f21f3-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
