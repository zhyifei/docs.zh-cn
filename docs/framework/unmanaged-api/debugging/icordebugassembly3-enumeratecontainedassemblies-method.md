---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 方法
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb84efe78568bbae03f76efc456fc8ae605e4db9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404827"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="43690-102">ICorDebugAssembly3::EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="43690-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="43690-103">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="43690-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43690-104">语法</span><span class="sxs-lookup"><span data-stu-id="43690-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43690-105">参数</span><span class="sxs-lookup"><span data-stu-id="43690-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="43690-106">[out]指向一个 ICorDebugAssemblyEnum 接口对象，它枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="43690-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43690-107">返回值</span><span class="sxs-lookup"><span data-stu-id="43690-107">Return Value</span></span>  
 <span data-ttu-id="43690-108">`S_OK` 若该 `ICorDebugAssembly3` 对象为容器；反之，`S_FALSE`，枚举为空。</span><span class="sxs-lookup"><span data-stu-id="43690-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43690-109">备注</span><span class="sxs-lookup"><span data-stu-id="43690-109">Remarks</span></span>  
 <span data-ttu-id="43690-110">需用符号来列举包含的程序集。</span><span class="sxs-lookup"><span data-stu-id="43690-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="43690-111">如果其并不存在，则方法返回 `S_FALSE`，且不提供有效枚举。</span><span class="sxs-lookup"><span data-stu-id="43690-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43690-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="43690-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43690-113">要求</span><span class="sxs-lookup"><span data-stu-id="43690-113">Requirements</span></span>  
 <span data-ttu-id="43690-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43690-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43690-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43690-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43690-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43690-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43690-117">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43690-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43690-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="43690-118">See Also</span></span>  
 [<span data-ttu-id="43690-119">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="43690-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="43690-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="43690-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
