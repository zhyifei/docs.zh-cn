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
ms.openlocfilehash: ee56a7f343de999d68a71d9eac04eed6e06b444e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568889"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="cf2ff-102">ICorDebugRegisterSet::GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="cf2ff-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="cf2ff-103">获取每个寄存器的值 （上当前正在执行代码的计算机） 指定的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="cf2ff-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf2ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="cf2ff-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="cf2ff-106">[in]一个位掩码，它指定要从中检索值的哪一寄存器。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="cf2ff-107">每位对应于寄存器。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="cf2ff-108">如果有些设置为 1，则检索寄存器的值;否则，不会检索寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="cf2ff-109">[in]要检索的注册值的数目。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="cf2ff-110">[out]一个数组`CORDB_REGISTER`对象，其中每个接收寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf2ff-111">备注</span><span class="sxs-lookup"><span data-stu-id="cf2ff-111">Remarks</span></span>  
 <span data-ttu-id="cf2ff-112">数组的大小应等于的位数设置为一个位掩码中。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="cf2ff-113">`regCount`参数指定将接收寄存器值的缓冲区中的元素数。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="cf2ff-114">如果`regCount`值指示掩码的寄存器数太小，将从集合中截断的更高版本的带编号的寄存器。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="cf2ff-115">如果`regCount`该值太大，而未使用`regBuffer`元素将保持不变。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="cf2ff-116">如果位掩码指定寄存器不可用，`GetRegisters`返回为该寄存器不确定的值。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf2ff-117">要求</span><span class="sxs-lookup"><span data-stu-id="cf2ff-117">Requirements</span></span>  
 <span data-ttu-id="cf2ff-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cf2ff-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf2ff-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf2ff-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf2ff-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf2ff-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf2ff-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf2ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2ff-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf2ff-122">See also</span></span>
- [<span data-ttu-id="cf2ff-123">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="cf2ff-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="cf2ff-124">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="cf2ff-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
