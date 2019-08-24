---
title: ICorDebugAssembly3::GetContainerAssembly 方法
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4cda67145a0e624f87e93cf02ebdb6bc77c34d2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69987605"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="cc604-102">ICorDebugAssembly3::GetContainerAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="cc604-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="cc604-103">返回该 `ICorDebugAssembly3` 对象的容器程序集。</span><span class="sxs-lookup"><span data-stu-id="cc604-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc604-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc604-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc604-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc604-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="cc604-106">指向表示容器程序集的 ICorDebugAssembly 对象地址的指针; 如果方法调用失败, 则为**null** 。</span><span class="sxs-lookup"><span data-stu-id="cc604-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc604-107">返回值</span><span class="sxs-lookup"><span data-stu-id="cc604-107">Return Value</span></span>  
 <span data-ttu-id="cc604-108">`S_OK`如果方法调用成功, 则为; 否则为。否则, `S_FALSE`和`ppAssembly`为**null**。</span><span class="sxs-lookup"><span data-stu-id="cc604-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc604-109">备注</span><span class="sxs-lookup"><span data-stu-id="cc604-109">Remarks</span></span>  
 <span data-ttu-id="cc604-110">如果程序集和单独容器程序集内的其他程序集合并，则方法返回容器程序集。</span><span class="sxs-lookup"><span data-stu-id="cc604-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="cc604-111">有关详细信息和术语, 请参阅[ICorDebugProcess6:: EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)主题。</span><span class="sxs-lookup"><span data-stu-id="cc604-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc604-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="cc604-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc604-113">要求</span><span class="sxs-lookup"><span data-stu-id="cc604-113">Requirements</span></span>  
 <span data-ttu-id="cc604-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc604-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc604-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="cc604-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc604-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc604-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc604-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc604-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc604-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc604-118">See also</span></span>

- [<span data-ttu-id="cc604-119">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="cc604-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="cc604-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="cc604-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
