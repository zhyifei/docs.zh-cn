---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 方法
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9120119056fda3f16b4a0bf8bad839b74463d633
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959330"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="39d91-102">ICorDebugAssembly3::EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="39d91-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="39d91-103">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="39d91-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39d91-104">语法</span><span class="sxs-lookup"><span data-stu-id="39d91-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39d91-105">参数</span><span class="sxs-lookup"><span data-stu-id="39d91-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="39d91-106">弄指向作为枚举器的 ICorDebugAssemblyEnum 接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="39d91-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39d91-107">返回值</span><span class="sxs-lookup"><span data-stu-id="39d91-107">Return Value</span></span>  
 <span data-ttu-id="39d91-108">`S_OK` 若该 `ICorDebugAssembly3` 对象为容器；反之，`S_FALSE`，枚举为空。</span><span class="sxs-lookup"><span data-stu-id="39d91-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39d91-109">备注</span><span class="sxs-lookup"><span data-stu-id="39d91-109">Remarks</span></span>  
 <span data-ttu-id="39d91-110">需用符号来列举包含的程序集。</span><span class="sxs-lookup"><span data-stu-id="39d91-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="39d91-111">如果其并不存在，则方法返回 `S_FALSE`，且不提供有效枚举。</span><span class="sxs-lookup"><span data-stu-id="39d91-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39d91-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="39d91-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39d91-113">要求</span><span class="sxs-lookup"><span data-stu-id="39d91-113">Requirements</span></span>  
 <span data-ttu-id="39d91-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="39d91-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39d91-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="39d91-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39d91-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39d91-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39d91-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39d91-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d91-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="39d91-118">See also</span></span>

- [<span data-ttu-id="39d91-119">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="39d91-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="39d91-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="39d91-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
