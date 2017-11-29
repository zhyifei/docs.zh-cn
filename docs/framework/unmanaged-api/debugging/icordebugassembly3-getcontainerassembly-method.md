---
title: "ICorDebugAssembly3::GetContainerAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f9a32520c2a67c0bc51a3f88e9822db49e4a3974
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="afcfe-102">ICorDebugAssembly3::GetContainerAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="afcfe-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="afcfe-103">返回该 `ICorDebugAssembly3` 对象的容器程序集。</span><span class="sxs-lookup"><span data-stu-id="afcfe-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afcfe-104">语法</span><span class="sxs-lookup"><span data-stu-id="afcfe-104">Syntax</span></span>  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="afcfe-105">参数</span><span class="sxs-lookup"><span data-stu-id="afcfe-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="afcfe-106">一个表示容器程序集，icor 调试程序集对象的地址的指针或**null**如果方法调用失败。</span><span class="sxs-lookup"><span data-stu-id="afcfe-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afcfe-107">返回值</span><span class="sxs-lookup"><span data-stu-id="afcfe-107">Return Value</span></span>  
 <span data-ttu-id="afcfe-108">`S_OK`如果方法调用成功;否则为`S_FALSE`，和`ppAssembly`是**null**。</span><span class="sxs-lookup"><span data-stu-id="afcfe-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afcfe-109">备注</span><span class="sxs-lookup"><span data-stu-id="afcfe-109">Remarks</span></span>  
 <span data-ttu-id="afcfe-110">如果程序集和单独容器程序集内的其他程序集合并，则方法返回容器程序集。</span><span class="sxs-lookup"><span data-stu-id="afcfe-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="afcfe-111">有关详细信息和术语，请参阅[icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)主题。</span><span class="sxs-lookup"><span data-stu-id="afcfe-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afcfe-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="afcfe-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afcfe-113">要求</span><span class="sxs-lookup"><span data-stu-id="afcfe-113">Requirements</span></span>  
 <span data-ttu-id="afcfe-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="afcfe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afcfe-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afcfe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afcfe-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afcfe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afcfe-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afcfe-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afcfe-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afcfe-118">See Also</span></span>  
 [<span data-ttu-id="afcfe-119">ICorDebugAssembly3 接口</span><span class="sxs-lookup"><span data-stu-id="afcfe-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [<span data-ttu-id="afcfe-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="afcfe-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
