---
title: ICorDebugNativeFrame::GetIP 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d17ac4230296674381c87851377fcb535837ad3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416814"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="f8176-102">ICorDebugNativeFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="f8176-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="f8176-103">获取本机代码偏移量为当前设置的指令指针的位置。</span><span class="sxs-lookup"><span data-stu-id="f8176-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8176-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8176-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8176-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8176-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="f8176-106">[out]指向本机代码中的偏移位置的指针。</span><span class="sxs-lookup"><span data-stu-id="f8176-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8176-107">备注</span><span class="sxs-lookup"><span data-stu-id="f8176-107">Remarks</span></span>  
 <span data-ttu-id="f8176-108">如果此"ICorDebugNativeFrame"表示的堆栈帧处于活动状态，偏移量是要执行的下一个指令的地址。</span><span class="sxs-lookup"><span data-stu-id="f8176-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="f8176-109">如果此堆栈帧不处于活动状态的偏移量是堆栈帧重新激活时要执行的下一个指令的地址。</span><span class="sxs-lookup"><span data-stu-id="f8176-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8176-110">要求</span><span class="sxs-lookup"><span data-stu-id="f8176-110">Requirements</span></span>  
 <span data-ttu-id="f8176-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8176-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8176-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8176-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8176-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8176-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8176-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8176-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8176-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8176-115">See Also</span></span>  
 
