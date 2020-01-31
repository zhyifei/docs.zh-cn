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
ms.openlocfilehash: c5fa0a67309e23c02393b70d849af3884dfd0adf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788543"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="edf1a-102">ICorDebugILFrame2 接口</span><span class="sxs-lookup"><span data-stu-id="edf1a-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="edf1a-103">ICorDebugILFrame 接口的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="edf1a-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="edf1a-104">方法</span><span class="sxs-lookup"><span data-stu-id="edf1a-104">Methods</span></span>  
  
|<span data-ttu-id="edf1a-105">方法</span><span class="sxs-lookup"><span data-stu-id="edf1a-105">Method</span></span>|<span data-ttu-id="edf1a-106">描述</span><span class="sxs-lookup"><span data-stu-id="edf1a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="edf1a-107">EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="edf1a-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="edf1a-108">获取一个 ICorDebugTypeEnum 对象，该对象包含此帧中的 <xref:System.Type> 参数。</span><span class="sxs-lookup"><span data-stu-id="edf1a-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="edf1a-109">RemapFunction 方法</span><span class="sxs-lookup"><span data-stu-id="edf1a-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="edf1a-110">通过指定新的 MSIL 偏移量重新映射编辑的函数。</span><span class="sxs-lookup"><span data-stu-id="edf1a-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edf1a-111">备注</span><span class="sxs-lookup"><span data-stu-id="edf1a-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edf1a-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="edf1a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edf1a-113">需求</span><span class="sxs-lookup"><span data-stu-id="edf1a-113">Requirements</span></span>  
 <span data-ttu-id="edf1a-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="edf1a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edf1a-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edf1a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edf1a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edf1a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edf1a-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edf1a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf1a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edf1a-118">See also</span></span>

- [<span data-ttu-id="edf1a-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="edf1a-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
