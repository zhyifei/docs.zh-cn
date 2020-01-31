---
title: ICorDebugAssembly3::GetContainerAssembly 方法
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 969cca6d5613670fc4b26fc973785b4874c3684c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778073"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="9df43-102">ICorDebugAssembly3::GetContainerAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="9df43-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="9df43-103">返回该 `ICorDebugAssembly3` 对象的容器程序集。</span><span class="sxs-lookup"><span data-stu-id="9df43-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9df43-104">语法</span><span class="sxs-lookup"><span data-stu-id="9df43-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9df43-105">参数</span><span class="sxs-lookup"><span data-stu-id="9df43-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="9df43-106">指向表示容器程序集的 ICorDebugAssembly 对象地址的指针; 如果方法调用失败，则为**null** 。</span><span class="sxs-lookup"><span data-stu-id="9df43-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9df43-107">返回值</span><span class="sxs-lookup"><span data-stu-id="9df43-107">Return Value</span></span>  
 <span data-ttu-id="9df43-108">如果方法调用成功，则为 `S_OK`;否则，`S_FALSE`和 `ppAssembly` 为**null**。</span><span class="sxs-lookup"><span data-stu-id="9df43-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9df43-109">备注</span><span class="sxs-lookup"><span data-stu-id="9df43-109">Remarks</span></span>  
 <span data-ttu-id="9df43-110">如果程序集和单独容器程序集内的其他程序集合并，则方法返回容器程序集。</span><span class="sxs-lookup"><span data-stu-id="9df43-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="9df43-111">有关详细信息和术语，请参阅[ICorDebugProcess6：： EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md)主题。</span><span class="sxs-lookup"><span data-stu-id="9df43-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9df43-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="9df43-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9df43-113">需求</span><span class="sxs-lookup"><span data-stu-id="9df43-113">Requirements</span></span>  
 <span data-ttu-id="9df43-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9df43-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9df43-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9df43-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9df43-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9df43-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9df43-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9df43-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df43-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9df43-118">See also</span></span>

- [<span data-ttu-id="9df43-119">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="9df43-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="9df43-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="9df43-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
