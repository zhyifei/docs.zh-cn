---
title: ICorDebugSymbolProvider2::GetFrameProps 方法
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: dc64152938c46945978715251286ecb6c6d8983c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791511"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="6ef02-102">ICorDebugSymbolProvider2::GetFrameProps 方法</span><span class="sxs-lookup"><span data-stu-id="6ef02-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="6ef02-103">返回启动方法相对虚拟地址的方法和具有代码相对虚拟地址的父框架。</span><span class="sxs-lookup"><span data-stu-id="6ef02-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef02-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ef02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ef02-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ef02-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="6ef02-106">[in] 代码相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="6ef02-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="6ef02-107">[out] 指向方法的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6ef02-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="6ef02-108">[out] 指向框架的启动相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6ef02-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef02-109">备注</span><span class="sxs-lookup"><span data-stu-id="6ef02-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ef02-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="6ef02-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef02-111">需求</span><span class="sxs-lookup"><span data-stu-id="6ef02-111">Requirements</span></span>  
 <span data-ttu-id="6ef02-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ef02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef02-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ef02-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ef02-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ef02-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ef02-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef02-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef02-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ef02-116">See also</span></span>

- [<span data-ttu-id="6ef02-117">ICorDebugSymbolProvider2 接口</span><span class="sxs-lookup"><span data-stu-id="6ef02-117">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="6ef02-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="6ef02-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
