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
ms.openlocfilehash: c0bdd9e59f5794dbb0d447dc2cc6cb682bfdf09f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008477"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="d0b02-102">LPOVERLAPPED_COMPLETION_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="d0b02-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="d0b02-103">指向一个函数，该函数在设备的重叠（即异步） i/o 完成时通知宿主。</span><span class="sxs-lookup"><span data-stu-id="d0b02-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="d0b02-104">此函数指针在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="d0b02-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b02-105">语法</span><span class="sxs-lookup"><span data-stu-id="d0b02-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0b02-106">参数</span><span class="sxs-lookup"><span data-stu-id="d0b02-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="d0b02-107">中如果设备已关闭，则为错误代码的值;否则，此值为零。</span><span class="sxs-lookup"><span data-stu-id="d0b02-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="d0b02-108">关闭设备会导致设备的所有挂起的 i/o 立即完成。</span><span class="sxs-lookup"><span data-stu-id="d0b02-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="d0b02-109">中I/o 操作传输的字节数。</span><span class="sxs-lookup"><span data-stu-id="d0b02-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="d0b02-110">中指向结构的指针，该结构包含用于完成 i/o 请求的信息。</span><span class="sxs-lookup"><span data-stu-id="d0b02-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0b02-111">备注</span><span class="sxs-lookup"><span data-stu-id="d0b02-111">Remarks</span></span>  
 <span data-ttu-id="d0b02-112">指向该函数的 `LPOVERLAPPED_COMPLETION_ROUTINE` 点是回调函数，并且必须由宿主应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="d0b02-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="d0b02-113">回调函数允许主机处理已完成的 i/o 请求。</span><span class="sxs-lookup"><span data-stu-id="d0b02-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b02-114">要求</span><span class="sxs-lookup"><span data-stu-id="d0b02-114">Requirements</span></span>  
 <span data-ttu-id="d0b02-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0b02-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b02-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d0b02-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0b02-117">**库：** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="d0b02-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d0b02-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b02-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b02-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0b02-119">See also</span></span>

- [<span data-ttu-id="d0b02-120">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="d0b02-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
