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
ms.openlocfilehash: 54a5fb50a0177fe9886582c112f16ce871ea9df4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792062"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="43e90-102">ICorDebugRegisterSet2::GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="43e90-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="43e90-103">获取由给定位掩码指定的每个寄存器（对于当前正在执行其代码的平台）的值。</span><span class="sxs-lookup"><span data-stu-id="43e90-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43e90-104">语法</span><span class="sxs-lookup"><span data-stu-id="43e90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43e90-105">参数</span><span class="sxs-lookup"><span data-stu-id="43e90-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="43e90-106">中`mask` 数组的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="43e90-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="43e90-107">中字节数组，其中每个位对应于寄存器。</span><span class="sxs-lookup"><span data-stu-id="43e90-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="43e90-108">如果位为1，则将检索相应寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="43e90-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="43e90-109">中要检索的寄存器值的数目。</span><span class="sxs-lookup"><span data-stu-id="43e90-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="43e90-110">弄`CORDB_REGISTER` 对象的数组，其中每个对象都接收寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="43e90-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43e90-111">备注</span><span class="sxs-lookup"><span data-stu-id="43e90-111">Remarks</span></span>  
 <span data-ttu-id="43e90-112">`GetRegisters` 方法从掩码指定的寄存器返回值的数组。</span><span class="sxs-lookup"><span data-stu-id="43e90-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="43e90-113">数组不包含掩码位未设置的寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="43e90-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="43e90-114">因此，`regBuffer` 数组的大小必须等于掩码中1的数目。</span><span class="sxs-lookup"><span data-stu-id="43e90-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="43e90-115">如果 `regCount` 的值对于掩码指定的寄存器数量太小，则将从该集中截断编号较高的寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="43e90-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="43e90-116">如果 `regCount` 太大，则不会修改未使用的 `regBuffer` 元素。</span><span class="sxs-lookup"><span data-stu-id="43e90-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="43e90-117">如果掩码指出某个不可用的寄存器，则将为该寄存器返回一个不确定的值。</span><span class="sxs-lookup"><span data-stu-id="43e90-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="43e90-118">对于包含64个以上寄存器的平台，`ICorDebugRegisterSet2::GetRegisters` 方法是必需的。</span><span class="sxs-lookup"><span data-stu-id="43e90-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="43e90-119">例如，IA64 具有128常规用途寄存器和128浮点寄存器，因此位掩码中需要超过64位。</span><span class="sxs-lookup"><span data-stu-id="43e90-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="43e90-120">如果寄存器不超过64，则与 x86 等平台上的情况一样，`GetRegisters` 方法实际上只是将 `mask` 字节数组中的字节转换为 `ULONG64`，然后调用[ICorDebugRegisterSet：： GetRegisters](icordebugregisterset-getregisters-method.md)方法，该方法采用 `ULONG64` 掩码。</span><span class="sxs-lookup"><span data-stu-id="43e90-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e90-121">需求</span><span class="sxs-lookup"><span data-stu-id="43e90-121">Requirements</span></span>  
 <span data-ttu-id="43e90-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43e90-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43e90-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43e90-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43e90-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43e90-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43e90-125">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43e90-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e90-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43e90-126">See also</span></span>

- [<span data-ttu-id="43e90-127">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="43e90-127">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="43e90-128">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="43e90-128">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
