---
title: ICorDebugILFrame2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
ms.openlocfilehash: 2e0f284625e99215900c6aaab94e4eae611787ed
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212095"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="1429c-102">ICorDebugILFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="1429c-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="1429c-103">ICorDebugILFrame 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="1429c-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1429c-104">方法</span><span class="sxs-lookup"><span data-stu-id="1429c-104">Methods</span></span>  
  
|<span data-ttu-id="1429c-105">方法</span><span class="sxs-lookup"><span data-stu-id="1429c-105">Method</span></span>|<span data-ttu-id="1429c-106">描述</span><span class="sxs-lookup"><span data-stu-id="1429c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1429c-107">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="1429c-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="1429c-108">获取一个 ICorDebugTypeEnum 对象，该对象包含 <xref:System.Type> 此帧中的参数。</span><span class="sxs-lookup"><span data-stu-id="1429c-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="1429c-109">RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="1429c-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="1429c-110">通过指定新的 MSIL 偏移量重新映射编辑的函数。</span><span class="sxs-lookup"><span data-stu-id="1429c-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1429c-111">备注</span><span class="sxs-lookup"><span data-stu-id="1429c-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1429c-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="1429c-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1429c-113">要求</span><span class="sxs-lookup"><span data-stu-id="1429c-113">Requirements</span></span>  
 <span data-ttu-id="1429c-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1429c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1429c-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1429c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1429c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1429c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1429c-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1429c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1429c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1429c-118">See also</span></span>

- [<span data-ttu-id="1429c-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="1429c-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
