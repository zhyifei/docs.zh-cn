---
title: LPOVERLAPPED_COMPLETION_ROUTINE 函数指针
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce2ce6dd1210eef94e77b5d6a2d58a35cf971e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765253"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="ddc98-102">LPOVERLAPPED_COMPLETION_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="ddc98-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="ddc98-103">指向通知主机时的重叠的函数 (即异步) 到设备的 I/O 已完成。</span><span class="sxs-lookup"><span data-stu-id="ddc98-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="ddc98-104">中已弃用此函数指针[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ddc98-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddc98-105">语法</span><span class="sxs-lookup"><span data-stu-id="ddc98-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddc98-106">参数</span><span class="sxs-lookup"><span data-stu-id="ddc98-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="ddc98-107">[in]一个值，如果设备已关闭; 是一个错误代码否则，此值为零。</span><span class="sxs-lookup"><span data-stu-id="ddc98-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="ddc98-108">关闭设备将导致所有挂起的设备对 i/o 操作立即完成。</span><span class="sxs-lookup"><span data-stu-id="ddc98-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="ddc98-109">[in]I/O 操作传输的字节数。</span><span class="sxs-lookup"><span data-stu-id="ddc98-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="ddc98-110">[in]指向包含要用来完成 I/O 请求的信息的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ddc98-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddc98-111">备注</span><span class="sxs-lookup"><span data-stu-id="ddc98-111">Remarks</span></span>  
 <span data-ttu-id="ddc98-112">该函数`LPOVERLAPPED_COMPLETION_ROUTINE`点是回调函数，必须由主机应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="ddc98-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ddc98-113">回调函数允许主机来处理已完成的 I/O 请求。</span><span class="sxs-lookup"><span data-stu-id="ddc98-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddc98-114">要求</span><span class="sxs-lookup"><span data-stu-id="ddc98-114">Requirements</span></span>  
 <span data-ttu-id="ddc98-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddc98-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddc98-116">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ddc98-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddc98-117">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="ddc98-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="ddc98-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddc98-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddc98-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddc98-119">See also</span></span>

- [<span data-ttu-id="ddc98-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="ddc98-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
