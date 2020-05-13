---
title: ICorDebugStaticFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: e36c94bf411e75f915cca86aee74cdf161674d25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379415"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="1c270-102">ICorDebugStaticFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="1c270-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="1c270-103">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="1c270-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c270-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c270-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c270-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c270-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="1c270-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="1c270-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c270-107">备注</span><span class="sxs-lookup"><span data-stu-id="1c270-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c270-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="1c270-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c270-109">要求</span><span class="sxs-lookup"><span data-stu-id="1c270-109">Requirements</span></span>  
 <span data-ttu-id="1c270-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c270-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c270-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c270-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c270-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c270-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c270-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c270-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c270-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c270-114">See also</span></span>

- [<span data-ttu-id="1c270-115">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="1c270-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="1c270-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="1c270-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
