---
title: ICorDebugFunction3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 71aa482cc2268da17f1376d8c305dd6a818d92d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213161"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="397f9-102">ICorDebugFunction3 接口</span><span class="sxs-lookup"><span data-stu-id="397f9-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="397f9-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="397f9-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="397f9-104">对 ICorDebugFunction 接口进行逻辑扩展，以提供对 ReJIT 请求中的代码的访问。</span><span class="sxs-lookup"><span data-stu-id="397f9-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="397f9-105">方法</span><span class="sxs-lookup"><span data-stu-id="397f9-105">Methods</span></span>  
  
|<span data-ttu-id="397f9-106">方法</span><span class="sxs-lookup"><span data-stu-id="397f9-106">Method</span></span>|<span data-ttu-id="397f9-107">描述</span><span class="sxs-lookup"><span data-stu-id="397f9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="397f9-108">GetActiveReJitRequestILCode 方法</span><span class="sxs-lookup"><span data-stu-id="397f9-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="397f9-109">获取一个接口指针，该指针指向包含活动 ReJIT 请求中的 IL 的[ICorDebugILCode](icordebugilcode-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="397f9-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="397f9-110">备注</span><span class="sxs-lookup"><span data-stu-id="397f9-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="397f9-111">要求</span><span class="sxs-lookup"><span data-stu-id="397f9-111">Requirements</span></span>  
 <span data-ttu-id="397f9-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="397f9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="397f9-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="397f9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="397f9-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="397f9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="397f9-115">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="397f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397f9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="397f9-116">See also</span></span>

- [<span data-ttu-id="397f9-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="397f9-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="397f9-118">调试</span><span class="sxs-lookup"><span data-stu-id="397f9-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="397f9-119">ReJIT：操作方法指南</span><span class="sxs-lookup"><span data-stu-id="397f9-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
