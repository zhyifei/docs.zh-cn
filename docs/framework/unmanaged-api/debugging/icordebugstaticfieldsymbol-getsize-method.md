---
title: ICorDebugStaticFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acb72a7d6c39efa5fa93bfddc314d07ec6cd8348
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419089"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="ba846-102">ICorDebugStaticFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="ba846-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="ba846-103">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ba846-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba846-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba846-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba846-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba846-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="ba846-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="ba846-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba846-107">备注</span><span class="sxs-lookup"><span data-stu-id="ba846-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba846-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="ba846-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba846-109">要求</span><span class="sxs-lookup"><span data-stu-id="ba846-109">Requirements</span></span>  
 <span data-ttu-id="ba846-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba846-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba846-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba846-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba846-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba846-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba846-113">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba846-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba846-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba846-114">See Also</span></span>  
 [<span data-ttu-id="ba846-115">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="ba846-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="ba846-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="ba846-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
