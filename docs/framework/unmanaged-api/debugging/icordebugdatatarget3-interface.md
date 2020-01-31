---
title: ICorDebugDataTarget3 接口
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783489"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="eecae-102">ICorDebugDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="eecae-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="eecae-103">对[ICorDebugDataTarget](icordebugdatatarget-interface.md)接口进行逻辑扩展，以提供有关已加载模块的信息。</span><span class="sxs-lookup"><span data-stu-id="eecae-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="eecae-104">方法</span><span class="sxs-lookup"><span data-stu-id="eecae-104">Method</span></span>  
  
|<span data-ttu-id="eecae-105">方法</span><span class="sxs-lookup"><span data-stu-id="eecae-105">Method</span></span>|<span data-ttu-id="eecae-106">描述</span><span class="sxs-lookup"><span data-stu-id="eecae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eecae-107">GetLoadedModules 方法</span><span class="sxs-lookup"><span data-stu-id="eecae-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="eecae-108">获取到目前为止已加载的模块的列表。</span><span class="sxs-lookup"><span data-stu-id="eecae-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eecae-109">备注</span><span class="sxs-lookup"><span data-stu-id="eecae-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eecae-110">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="eecae-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="eecae-111">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="eecae-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eecae-112">需求</span><span class="sxs-lookup"><span data-stu-id="eecae-112">Requirements</span></span>  
 <span data-ttu-id="eecae-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eecae-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eecae-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eecae-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eecae-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eecae-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eecae-116">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eecae-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eecae-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eecae-117">See also</span></span>

- [<span data-ttu-id="eecae-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="eecae-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="eecae-119">调试</span><span class="sxs-lookup"><span data-stu-id="eecae-119">Debugging</span></span>](index.md)
