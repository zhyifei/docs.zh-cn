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
ms.openlocfilehash: 53576ca938074fb7e5974a96bb53a84cb6ed67ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213590"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="67bbc-102">ICorDebugNativeFrame::GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="67bbc-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="67bbc-103">获取指令指针当前所设置到的本机代码偏移位置。</span><span class="sxs-lookup"><span data-stu-id="67bbc-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67bbc-104">语法</span><span class="sxs-lookup"><span data-stu-id="67bbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67bbc-105">参数</span><span class="sxs-lookup"><span data-stu-id="67bbc-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="67bbc-106">弄指向本机代码中的偏移位置的指针。</span><span class="sxs-lookup"><span data-stu-id="67bbc-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67bbc-107">备注</span><span class="sxs-lookup"><span data-stu-id="67bbc-107">Remarks</span></span>  
 <span data-ttu-id="67bbc-108">如果此 "ICorDebugNativeFrame" 表示的堆栈帧处于活动状态，则偏移量是要执行的下一条指令的地址。</span><span class="sxs-lookup"><span data-stu-id="67bbc-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="67bbc-109">如果此堆栈帧不处于活动状态，则偏移量是在重新激活堆栈帧时要执行的下一条指令的地址。</span><span class="sxs-lookup"><span data-stu-id="67bbc-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67bbc-110">要求</span><span class="sxs-lookup"><span data-stu-id="67bbc-110">Requirements</span></span>  
 <span data-ttu-id="67bbc-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67bbc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67bbc-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67bbc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67bbc-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67bbc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67bbc-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67bbc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67bbc-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="67bbc-115">See also</span></span>
