---
title: "ICorDebugSymbolProvider2::GetFrameProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3892b8da3286132709792513f055d6ce75bd3fce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="eb679-102">ICorDebugSymbolProvider2::GetFrameProps 方法</span><span class="sxs-lookup"><span data-stu-id="eb679-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="eb679-103">返回启动方法相对虚拟地址的方法和具有代码相对虚拟地址的父框架。</span><span class="sxs-lookup"><span data-stu-id="eb679-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb679-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb679-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb679-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb679-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="eb679-106">[in] 代码相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="eb679-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="eb679-107">[out] 指向方法的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="eb679-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="eb679-108">[out] 指向框架的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="eb679-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb679-109">备注</span><span class="sxs-lookup"><span data-stu-id="eb679-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb679-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="eb679-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb679-111">要求</span><span class="sxs-lookup"><span data-stu-id="eb679-111">Requirements</span></span>  
 <span data-ttu-id="eb679-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb679-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb679-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb679-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb679-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb679-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb679-115">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb679-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb679-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb679-116">See Also</span></span>  
 [<span data-ttu-id="eb679-117">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="eb679-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="eb679-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="eb679-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
