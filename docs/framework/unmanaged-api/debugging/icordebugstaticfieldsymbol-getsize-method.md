---
title: ICorDebugStaticFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: deeb887dad38417e3ebb980f5ef2f89392388d65
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791810"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="af51f-102">ICorDebugStaticFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="af51f-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="af51f-103">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="af51f-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af51f-104">语法</span><span class="sxs-lookup"><span data-stu-id="af51f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af51f-105">参数</span><span class="sxs-lookup"><span data-stu-id="af51f-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="af51f-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="af51f-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af51f-107">备注</span><span class="sxs-lookup"><span data-stu-id="af51f-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af51f-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="af51f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af51f-109">需求</span><span class="sxs-lookup"><span data-stu-id="af51f-109">Requirements</span></span>  
 <span data-ttu-id="af51f-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af51f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af51f-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af51f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af51f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af51f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af51f-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af51f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af51f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af51f-114">See also</span></span>

- [<span data-ttu-id="af51f-115">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="af51f-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="af51f-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="af51f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
