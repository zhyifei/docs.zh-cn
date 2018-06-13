---
title: ICorDebugAssembly3::GetContainerAssembly 方法
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acb34ac2568ac88797441306820e6e762b5ac46e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409722"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="d1552-102">ICorDebugAssembly3::GetContainerAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="d1552-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="d1552-103">返回该 `ICorDebugAssembly3` 对象的容器程序集。</span><span class="sxs-lookup"><span data-stu-id="d1552-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1552-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1552-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d1552-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1552-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="d1552-106">一个表示容器程序集，icor 调试程序集对象的地址的指针或**null**如果方法调用失败。</span><span class="sxs-lookup"><span data-stu-id="d1552-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1552-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d1552-107">Return Value</span></span>  
 <span data-ttu-id="d1552-108">`S_OK` 如果方法调用成功;否则为`S_FALSE`，和`ppAssembly`是**null**。</span><span class="sxs-lookup"><span data-stu-id="d1552-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1552-109">备注</span><span class="sxs-lookup"><span data-stu-id="d1552-109">Remarks</span></span>  
 <span data-ttu-id="d1552-110">如果程序集和单独容器程序集内的其他程序集合并，则方法返回容器程序集。</span><span class="sxs-lookup"><span data-stu-id="d1552-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="d1552-111">有关详细信息和术语，请参阅[icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d1552-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1552-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="d1552-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1552-113">要求</span><span class="sxs-lookup"><span data-stu-id="d1552-113">Requirements</span></span>  
 <span data-ttu-id="d1552-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1552-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1552-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1552-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1552-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1552-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1552-117">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1552-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1552-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1552-118">See Also</span></span>  
 [<span data-ttu-id="d1552-119">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="d1552-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="d1552-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="d1552-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
