---
title: "ICorDebugNativeFrame::GetIP 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ceb0188ce2a52c3950b5fc89ea15c96852910d88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="127ce-102">ICorDebugNativeFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="127ce-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="127ce-103">获取本机代码偏移量为当前设置的指令指针的位置。</span><span class="sxs-lookup"><span data-stu-id="127ce-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127ce-104">语法</span><span class="sxs-lookup"><span data-stu-id="127ce-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="127ce-105">参数</span><span class="sxs-lookup"><span data-stu-id="127ce-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="127ce-106">[out]指向本机代码中的偏移位置的指针。</span><span class="sxs-lookup"><span data-stu-id="127ce-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="127ce-107">备注</span><span class="sxs-lookup"><span data-stu-id="127ce-107">Remarks</span></span>  
 <span data-ttu-id="127ce-108">如果此"ICorDebugNativeFrame"表示的堆栈帧处于活动状态，偏移量是要执行的下一个指令的地址。</span><span class="sxs-lookup"><span data-stu-id="127ce-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="127ce-109">如果此堆栈帧不处于活动状态的偏移量是堆栈帧重新激活时要执行的下一个指令的地址。</span><span class="sxs-lookup"><span data-stu-id="127ce-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="127ce-110">要求</span><span class="sxs-lookup"><span data-stu-id="127ce-110">Requirements</span></span>  
 <span data-ttu-id="127ce-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="127ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="127ce-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="127ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="127ce-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="127ce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="127ce-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="127ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="127ce-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="127ce-115">See Also</span></span>  
 
