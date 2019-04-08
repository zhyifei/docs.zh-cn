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
ms.openlocfilehash: 38f913b742f7ece2f136454f801ae780124aed87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073528"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="75fab-102">ICorDebugNativeFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="75fab-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="75fab-103">获取本机代码偏移量为当前设置的指令指针的位置。</span><span class="sxs-lookup"><span data-stu-id="75fab-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fab-104">语法</span><span class="sxs-lookup"><span data-stu-id="75fab-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75fab-105">参数</span><span class="sxs-lookup"><span data-stu-id="75fab-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="75fab-106">[out]指向本机代码中的偏移量位置的指针。</span><span class="sxs-lookup"><span data-stu-id="75fab-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75fab-107">备注</span><span class="sxs-lookup"><span data-stu-id="75fab-107">Remarks</span></span>  
 <span data-ttu-id="75fab-108">如果此"ICorDebugNativeFrame"表示的堆栈帧处于活动状态，偏移量为下一步要执行的指令的地址。</span><span class="sxs-lookup"><span data-stu-id="75fab-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="75fab-109">如果此堆栈帧未处于活动状态，偏移量为堆栈帧重新激活时要执行的下一个指令的地址。</span><span class="sxs-lookup"><span data-stu-id="75fab-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75fab-110">要求</span><span class="sxs-lookup"><span data-stu-id="75fab-110">Requirements</span></span>  
 <span data-ttu-id="75fab-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75fab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75fab-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75fab-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75fab-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75fab-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="75fab-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="75fab-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75fab-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="75fab-115">See also</span></span>
