---
title: ICorDebugAssembly3::EnumerateContainedAssemblies 方法
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080951"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="953cb-102">ICorDebugAssembly3::EnumerateContainedAssemblies 方法</span><span class="sxs-lookup"><span data-stu-id="953cb-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="953cb-103">获取该程序集中所包含的程序集的枚举器。</span><span class="sxs-lookup"><span data-stu-id="953cb-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="953cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="953cb-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="953cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="953cb-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="953cb-106">[out]指向一个 ICorDebugAssemblyEnum 接口对象，它枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="953cb-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="953cb-107">返回值</span><span class="sxs-lookup"><span data-stu-id="953cb-107">Return Value</span></span>  
 <span data-ttu-id="953cb-108">`S_OK` 若该 `ICorDebugAssembly3` 对象为容器；反之，`S_FALSE`，枚举为空。</span><span class="sxs-lookup"><span data-stu-id="953cb-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="953cb-109">备注</span><span class="sxs-lookup"><span data-stu-id="953cb-109">Remarks</span></span>  
 <span data-ttu-id="953cb-110">需用符号来列举包含的程序集。</span><span class="sxs-lookup"><span data-stu-id="953cb-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="953cb-111">如果其并不存在，则方法返回 `S_FALSE`，且不提供有效枚举。</span><span class="sxs-lookup"><span data-stu-id="953cb-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="953cb-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="953cb-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953cb-113">要求</span><span class="sxs-lookup"><span data-stu-id="953cb-113">Requirements</span></span>  
 <span data-ttu-id="953cb-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="953cb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="953cb-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="953cb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="953cb-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="953cb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="953cb-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="953cb-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953cb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="953cb-118">See also</span></span>

- [<span data-ttu-id="953cb-119">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="953cb-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="953cb-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="953cb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
