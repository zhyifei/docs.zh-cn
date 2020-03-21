---
title: ICorDebugRegisterSet::GetRegisters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 32e899622b9c649a08e3bca1b6645f70dcbcbb19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178542"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="3df46-102">ICorDebugRegisterSet::GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="3df46-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="3df46-103">获取位掩码指定的每个寄存器的值（当前正在执行代码的计算机）。</span><span class="sxs-lookup"><span data-stu-id="3df46-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df46-104">语法</span><span class="sxs-lookup"><span data-stu-id="3df46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3df46-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3df46-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="3df46-106">[在]指定要检索哪些寄存器值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="3df46-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="3df46-107">每个位对应于寄存器。</span><span class="sxs-lookup"><span data-stu-id="3df46-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="3df46-108">如果位设置为 1，则检索寄存器的值;如果位设置为 1，则检索寄存器的值。否则，不会检索寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="3df46-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="3df46-109">[在]要检索的寄存器值数。</span><span class="sxs-lookup"><span data-stu-id="3df46-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="3df46-110">[出]对象数组`CORDB_REGISTER`，每个对象都接收寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="3df46-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3df46-111">备注</span><span class="sxs-lookup"><span data-stu-id="3df46-111">Remarks</span></span>  
 <span data-ttu-id="3df46-112">数组的大小应等于位掩码中设置为 1 的位数。</span><span class="sxs-lookup"><span data-stu-id="3df46-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="3df46-113">参数`regCount`指定将接收寄存器值的缓冲区中的元素数。</span><span class="sxs-lookup"><span data-stu-id="3df46-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="3df46-114">如果`regCount`该值对于掩码指示的寄存器数太小，则较高的编号寄存器将从集中截断。</span><span class="sxs-lookup"><span data-stu-id="3df46-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="3df46-115">如果`regCount`该值太大，则未使用`regBuffer`的元素将取消修改。</span><span class="sxs-lookup"><span data-stu-id="3df46-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="3df46-116">如果位掩码指定不可用的寄存器，`GetRegisters`则返回该寄存器的不确定值。</span><span class="sxs-lookup"><span data-stu-id="3df46-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3df46-117">要求</span><span class="sxs-lookup"><span data-stu-id="3df46-117">Requirements</span></span>  
 <span data-ttu-id="3df46-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3df46-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3df46-119">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3df46-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3df46-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3df46-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3df46-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3df46-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df46-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3df46-122">See also</span></span>

- [<span data-ttu-id="3df46-123">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="3df46-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="3df46-124">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="3df46-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
