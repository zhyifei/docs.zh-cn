---
title: ICLRDataTarget::SetTLSValue 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 421fb371094c21948486e56d0881163e7a6961a0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465278"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="fb7e5-102">ICLRDataTarget::SetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="fb7e5-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="fb7e5-103">设置中指定目标进程中线程的线程本地存储 (TLS) 的值。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="fb7e5-104">由公共语言运行时 (CLR) 数据访问服务调用此方法。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7e5-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb7e5-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb7e5-106">参数</span><span class="sxs-lookup"><span data-stu-id="fb7e5-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="fb7e5-107">[in]目标进程中线程的操作系统的系统标识符。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="fb7e5-108">[in]位置的索引。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-108">[in] The index of the location.</span></span> <span data-ttu-id="fb7e5-109">此值必须是线程的指定本地存储中的有效索引。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="fb7e5-110">[in]一个`CLRDATA_ADDRESS`值，该值指定要放置在给定的 TLS 位置的值。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb7e5-111">备注</span><span class="sxs-lookup"><span data-stu-id="fb7e5-111">Remarks</span></span>  
 <span data-ttu-id="fb7e5-112">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb7e5-113">要求</span><span class="sxs-lookup"><span data-stu-id="fb7e5-113">Requirements</span></span>  
 <span data-ttu-id="fb7e5-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb7e5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb7e5-115">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="fb7e5-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="fb7e5-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb7e5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb7e5-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7e5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb7e5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb7e5-118">See also</span></span>
- [<span data-ttu-id="fb7e5-119">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="fb7e5-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
