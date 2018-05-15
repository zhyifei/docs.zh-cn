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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deaeb4e244a4f9c1e8582d9bea26c2ae5cfde818
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="874de-102">ICorDebugRegisterSet::GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="874de-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="874de-103">（在计算机上当前正在执行代码） 中获取的每个寄存器的值指定的位掩码。</span><span class="sxs-lookup"><span data-stu-id="874de-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874de-104">语法</span><span class="sxs-lookup"><span data-stu-id="874de-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="874de-105">参数</span><span class="sxs-lookup"><span data-stu-id="874de-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="874de-106">[in]指定哪一寄存器的值为要检索一个位掩码。</span><span class="sxs-lookup"><span data-stu-id="874de-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="874de-107">每位对应于寄存器。</span><span class="sxs-lookup"><span data-stu-id="874de-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="874de-108">如果位设置为 1，则检索寄存器的值;否则，不会检索寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="874de-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="874de-109">[in]要检索的寄存器值的数目。</span><span class="sxs-lookup"><span data-stu-id="874de-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="874de-110">[out]数组`CORDB_REGISTER`对象，其中每个接收的寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="874de-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="874de-111">备注</span><span class="sxs-lookup"><span data-stu-id="874de-111">Remarks</span></span>  
 <span data-ttu-id="874de-112">数组的大小应等于的中位掩码设置为 1 的位数。</span><span class="sxs-lookup"><span data-stu-id="874de-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="874de-113">`regCount`参数指定将接收寄存器值的缓冲区中的元素数。</span><span class="sxs-lookup"><span data-stu-id="874de-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="874de-114">如果`regCount`值是由屏蔽指示的寄存器的数目太小，将从集合中截断的更高版本的编号的寄存器。</span><span class="sxs-lookup"><span data-stu-id="874de-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="874de-115">如果`regCount`值太大，未使用`regBuffer`元素将保持不变。</span><span class="sxs-lookup"><span data-stu-id="874de-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="874de-116">如果位掩码指定不可用，注册`GetRegisters`返回该寄存器的不确定的值。</span><span class="sxs-lookup"><span data-stu-id="874de-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="874de-117">要求</span><span class="sxs-lookup"><span data-stu-id="874de-117">Requirements</span></span>  
 <span data-ttu-id="874de-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="874de-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="874de-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="874de-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="874de-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="874de-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="874de-121">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="874de-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874de-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="874de-122">See Also</span></span>  
 [<span data-ttu-id="874de-123">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="874de-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="874de-124">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="874de-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
