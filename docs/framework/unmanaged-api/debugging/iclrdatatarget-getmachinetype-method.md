---
title: "ICLRDataTarget::GetMachineType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetMachineType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetMachineType
helpviewer_keywords:
- ICLRDataTarget::GetMachineType method [.NET Framework debugging]
- GetMachineType method [.NET Framework debugging]
ms.assetid: 5f1f9c61-3e3b-48b2-b111-a4395f7623a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56fabfd2bb929e40c60903ad7b5e86e2b18d7d93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetmachinetype-method"></a><span data-ttu-id="e7a0a-102">ICLRDataTarget::GetMachineType 方法</span><span class="sxs-lookup"><span data-stu-id="e7a0a-102">ICLRDataTarget::GetMachineType Method</span></span>
<span data-ttu-id="e7a0a-103">获取目标进程正在使用的指令集的种类的标识符。</span><span class="sxs-lookup"><span data-stu-id="e7a0a-103">Gets the identifier for the kind of instruction set that the target process is using.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7a0a-104">Syntax</span></span>  
  
```  
HRESULT GetMachineType (  
    [out] ULONG32     *machineType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7a0a-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7a0a-105">Parameters</span></span>  
 `machineType`  
 <span data-ttu-id="e7a0a-106">[out]指向一个值，指示的指令集的目标进程正在使用。</span><span class="sxs-lookup"><span data-stu-id="e7a0a-106">[out] A pointer to a value that indicates the instruction set that the target process is using.</span></span> <span data-ttu-id="e7a0a-107">返回`machineType`是在 WinNT.h 中的标头文件中定义的 IMAGE_FILE_MACHINE 常量之一。</span><span class="sxs-lookup"><span data-stu-id="e7a0a-107">The returned `machineType` is one of the IMAGE_FILE_MACHINE constants, which are defined in the WinNT.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7a0a-108">惠?</span><span class="sxs-lookup"><span data-stu-id="e7a0a-108">Requirements</span></span>  
 <span data-ttu-id="e7a0a-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7a0a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7a0a-110">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e7a0a-110">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e7a0a-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7a0a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7a0a-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7a0a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a0a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7a0a-113">See Also</span></span>  
 [<span data-ttu-id="e7a0a-114">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e7a0a-114">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
