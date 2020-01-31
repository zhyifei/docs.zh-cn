---
title: ICorDebugRegisterSet2::GetRegistersAvailable 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
ms.openlocfilehash: 00c9939b25f395010f6ea5832b405c3e9928a223
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792029"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="8450f-102">ICorDebugRegisterSet2::GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="8450f-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="8450f-103">获取提供可用寄存器的位图的字节数组。</span><span class="sxs-lookup"><span data-stu-id="8450f-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8450f-104">语法</span><span class="sxs-lookup"><span data-stu-id="8450f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8450f-105">参数</span><span class="sxs-lookup"><span data-stu-id="8450f-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="8450f-106">[in] `availableRegChunks` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="8450f-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="8450f-107">弄字节数组，其中每个位对应于寄存器。</span><span class="sxs-lookup"><span data-stu-id="8450f-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="8450f-108">如果寄存器可用，则会设置寄存器的相应位。</span><span class="sxs-lookup"><span data-stu-id="8450f-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8450f-109">备注</span><span class="sxs-lookup"><span data-stu-id="8450f-109">Remarks</span></span>  
 <span data-ttu-id="8450f-110">CorDebugRegister 枚举的值指定不同微处理器的寄存器。</span><span class="sxs-lookup"><span data-stu-id="8450f-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="8450f-111">每个值的上限为 `availableRegChunks` 字节数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="8450f-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="8450f-112">每个值的下三位标识索引字节内的位位置。</span><span class="sxs-lookup"><span data-stu-id="8450f-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="8450f-113">给定一个指定特定寄存器的 `CorDebugRegister` 值时，将按如下所示确定此寄存器在掩码中的位置：</span><span class="sxs-lookup"><span data-stu-id="8450f-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="8450f-114">提取访问 `availableRegChunks` 数组中正确字节所需的索引：</span><span class="sxs-lookup"><span data-stu-id="8450f-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="8450f-115">`CorDebugRegister` 值 > > 3</span><span class="sxs-lookup"><span data-stu-id="8450f-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="8450f-116">提取索引字节内的位位置，其中位零是最小有效位：</span><span class="sxs-lookup"><span data-stu-id="8450f-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="8450f-117">`CorDebugRegister` 值 & 7</span><span class="sxs-lookup"><span data-stu-id="8450f-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8450f-118">需求</span><span class="sxs-lookup"><span data-stu-id="8450f-118">Requirements</span></span>  
 <span data-ttu-id="8450f-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8450f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8450f-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8450f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8450f-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8450f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8450f-122">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8450f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8450f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8450f-123">See also</span></span>

- [<span data-ttu-id="8450f-124">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="8450f-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="8450f-125">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="8450f-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
