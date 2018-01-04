---
title: "ICorDebugRegisterSet2::GetRegistersAvailable 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e2e3862f91fc68879e2f9e396ab9045c617de82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="ea45f-102">ICorDebugRegisterSet2::GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="ea45f-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="ea45f-103">获取提供的可用寄存器位图的字节数组。</span><span class="sxs-lookup"><span data-stu-id="ea45f-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea45f-104">语法</span><span class="sxs-lookup"><span data-stu-id="ea45f-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea45f-105">参数</span><span class="sxs-lookup"><span data-stu-id="ea45f-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="ea45f-106">[in] `availableRegChunks` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="ea45f-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="ea45f-107">[out]字节数组，其中每位对应于寄存器。</span><span class="sxs-lookup"><span data-stu-id="ea45f-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="ea45f-108">如果可用的寄存器，注册的对应位将设置。</span><span class="sxs-lookup"><span data-stu-id="ea45f-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea45f-109">备注</span><span class="sxs-lookup"><span data-stu-id="ea45f-109">Remarks</span></span>  
 <span data-ttu-id="ea45f-110">CorDebugRegister 枚举的值指定不同微处理器的寄存器。</span><span class="sxs-lookup"><span data-stu-id="ea45f-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="ea45f-111">每个值的上限五位均为的索引为`availableRegChunks`的字节数组。</span><span class="sxs-lookup"><span data-stu-id="ea45f-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="ea45f-112">每个值的较低的三个位标识中的索引的字节的位位置。</span><span class="sxs-lookup"><span data-stu-id="ea45f-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="ea45f-113">给定`CorDebugRegister`值，该值指定特定的注册，掩码中的寄存器的位置确定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea45f-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="ea45f-114">提取所需访问中的正确字节的索引`availableRegChunks`数组：</span><span class="sxs-lookup"><span data-stu-id="ea45f-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="ea45f-115">`CorDebugRegister`值 >> 3</span><span class="sxs-lookup"><span data-stu-id="ea45f-115">`CorDebugRegister` value >> 3</span></span>  
  
2.  <span data-ttu-id="ea45f-116">提取其中位零是最低有效位的位位置中的索引的字节：</span><span class="sxs-lookup"><span data-stu-id="ea45f-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="ea45f-117">`CorDebugRegister`值 （&) 7</span><span class="sxs-lookup"><span data-stu-id="ea45f-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea45f-118">惠?</span><span class="sxs-lookup"><span data-stu-id="ea45f-118">Requirements</span></span>  
 <span data-ttu-id="ea45f-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea45f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea45f-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea45f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea45f-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea45f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea45f-122">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea45f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea45f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea45f-123">See Also</span></span>  
 [<span data-ttu-id="ea45f-124">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="ea45f-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="ea45f-125">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="ea45f-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
