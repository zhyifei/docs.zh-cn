---
title: ICorDebugStaticFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d99e06c1093dbc67e9c1999e4b9ccabd6579340e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962662"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="b8e8d-102">ICorDebugStaticFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="b8e8d-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="b8e8d-103">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b8e8d-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8e8d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8e8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="b8e8d-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="b8e8d-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="b8e8d-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8e8d-107">备注</span><span class="sxs-lookup"><span data-stu-id="b8e8d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8e8d-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b8e8d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8e8d-109">要求</span><span class="sxs-lookup"><span data-stu-id="b8e8d-109">Requirements</span></span>  
 <span data-ttu-id="b8e8d-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8e8d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e8d-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="b8e8d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8e8d-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8e8d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8e8d-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e8d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e8d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e8d-114">See also</span></span>

- [<span data-ttu-id="b8e8d-115">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="b8e8d-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="b8e8d-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="b8e8d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
