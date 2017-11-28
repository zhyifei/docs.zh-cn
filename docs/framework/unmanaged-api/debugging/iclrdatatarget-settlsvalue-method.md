---
title: "ICLRDataTarget::SetTLSValue 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.SetTLSValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75c9d25b496e300d66844e3fd88655ab38da4b0e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="49370-102">ICLRDataTarget::SetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="49370-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="49370-103">设置一个值以指定目标进程中线程的线程本地存储 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="49370-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="49370-104">由公共语言运行时 (CLR) 数据访问服务调用此方法。</span><span class="sxs-lookup"><span data-stu-id="49370-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49370-105">语法</span><span class="sxs-lookup"><span data-stu-id="49370-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49370-106">参数</span><span class="sxs-lookup"><span data-stu-id="49370-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="49370-107">[in]目标进程中线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="49370-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="49370-108">[in]位置的索引。</span><span class="sxs-lookup"><span data-stu-id="49370-108">[in] The index of the location.</span></span> <span data-ttu-id="49370-109">此值必须是线程的指定的本地存储中的有效索引。</span><span class="sxs-lookup"><span data-stu-id="49370-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="49370-110">[in]A`CLRDATA_ADDRESS`值，该值指定要将放在给定的 TLS 位置的值。</span><span class="sxs-lookup"><span data-stu-id="49370-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49370-111">备注</span><span class="sxs-lookup"><span data-stu-id="49370-111">Remarks</span></span>  
 <span data-ttu-id="49370-112">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="49370-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49370-113">要求</span><span class="sxs-lookup"><span data-stu-id="49370-113">Requirements</span></span>  
 <span data-ttu-id="49370-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49370-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49370-115">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="49370-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="49370-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49370-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49370-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49370-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49370-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49370-118">See Also</span></span>  
 [<span data-ttu-id="49370-119">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="49370-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
