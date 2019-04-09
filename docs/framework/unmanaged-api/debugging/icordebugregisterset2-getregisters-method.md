---
title: ICorDebugRegisterSet2::GetRegisters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2dc1064656f3493db78d858cf1e86db0cb83d6c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136690"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="2897a-102">ICorDebugRegisterSet2::GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="2897a-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="2897a-103">（适用于当前执行代码的平台） 获取每个寄存器的值指定的给定的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2897a-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2897a-104">语法</span><span class="sxs-lookup"><span data-stu-id="2897a-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2897a-105">参数</span><span class="sxs-lookup"><span data-stu-id="2897a-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="2897a-106">[in]大小，以字节为单位的`mask`数组。</span><span class="sxs-lookup"><span data-stu-id="2897a-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="2897a-107">[in]一个字节数组，其中每位对应于寄存器。</span><span class="sxs-lookup"><span data-stu-id="2897a-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="2897a-108">如果位是 1，将检索相应寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="2897a-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="2897a-109">[in]要检索的注册值的数目。</span><span class="sxs-lookup"><span data-stu-id="2897a-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="2897a-110">[out]一个数组`CORDB_REGISTER`对象，其中每个接收寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="2897a-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2897a-111">备注</span><span class="sxs-lookup"><span data-stu-id="2897a-111">Remarks</span></span>  
 <span data-ttu-id="2897a-112">`GetRegisters`方法返回从指定的掩码的寄存器的值的数组。</span><span class="sxs-lookup"><span data-stu-id="2897a-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="2897a-113">数组不包含未设置其掩码位寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="2897a-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="2897a-114">因此，大小`regBuffer`数组必须是等于 1 的数掩码中。</span><span class="sxs-lookup"><span data-stu-id="2897a-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="2897a-115">如果的值`regCount`是太小，用于将从集合中截断的掩码，较高的带编号寄存器的值指示的寄存器的数量。</span><span class="sxs-lookup"><span data-stu-id="2897a-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="2897a-116">如果`regCount`太大，未使用`regBuffer`元素将保持不变。</span><span class="sxs-lookup"><span data-stu-id="2897a-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="2897a-117">如果掩码指示寄存器不可用，将为该寄存器返回不确定的值。</span><span class="sxs-lookup"><span data-stu-id="2897a-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="2897a-118">`ICorDebugRegisterSet2::GetRegisters`是必要的平台具有 64 个以上寄存器的方法。</span><span class="sxs-lookup"><span data-stu-id="2897a-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="2897a-119">例如，IA64 具有 128 个通用寄存器和 128 的浮点寄存器，因此你需要更多的位掩码中的 64 位。</span><span class="sxs-lookup"><span data-stu-id="2897a-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="2897a-120">如果这种情况，如 x86 平台上不具有 64 个以上寄存器`GetRegisters`方法实际上就是将转换中的字节`mask`到字节数组`ULONG64`，然后调用[ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)方法，它使用`ULONG64`掩码。</span><span class="sxs-lookup"><span data-stu-id="2897a-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2897a-121">要求</span><span class="sxs-lookup"><span data-stu-id="2897a-121">Requirements</span></span>  
 <span data-ttu-id="2897a-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2897a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2897a-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2897a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2897a-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2897a-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2897a-125">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2897a-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2897a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2897a-126">See also</span></span>

- [<span data-ttu-id="2897a-127">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="2897a-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="2897a-128">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="2897a-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
