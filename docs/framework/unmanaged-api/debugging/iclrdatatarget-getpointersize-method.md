---
title: "ICLRDataTarget::GetPointerSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4ca35246b82ed4adc982b6e7b157398d230dabe4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="83e5a-102">ICLRDataTarget::GetPointerSize 方法</span><span class="sxs-lookup"><span data-stu-id="83e5a-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="83e5a-103">获取大小，以字节为单位，则目标进程将使用与指针类型。</span><span class="sxs-lookup"><span data-stu-id="83e5a-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="83e5a-104">由公共语言运行时数据访问服务调用此方法。</span><span class="sxs-lookup"><span data-stu-id="83e5a-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e5a-105">语法</span><span class="sxs-lookup"><span data-stu-id="83e5a-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83e5a-106">参数</span><span class="sxs-lookup"><span data-stu-id="83e5a-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="83e5a-107">[out]指向一个整数值，指定大小，以字节为单位，在目标进程的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="83e5a-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83e5a-108">备注</span><span class="sxs-lookup"><span data-stu-id="83e5a-108">Remarks</span></span>  
 <span data-ttu-id="83e5a-109">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="83e5a-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e5a-110">惠?</span><span class="sxs-lookup"><span data-stu-id="83e5a-110">Requirements</span></span>  
 <span data-ttu-id="83e5a-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83e5a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e5a-112">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="83e5a-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="83e5a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83e5a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83e5a-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83e5a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e5a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="83e5a-115">See Also</span></span>  
 [<span data-ttu-id="83e5a-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="83e5a-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
