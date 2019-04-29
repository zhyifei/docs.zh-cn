---
title: ICorDebugStaticFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9baa3632b6ede9ce45f34302611710344ed33761
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782598"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="10389-102">ICorDebugStaticFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="10389-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="10389-103">获取静态字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="10389-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10389-104">语法</span><span class="sxs-lookup"><span data-stu-id="10389-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10389-105">参数</span><span class="sxs-lookup"><span data-stu-id="10389-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="10389-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="10389-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10389-107">备注</span><span class="sxs-lookup"><span data-stu-id="10389-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10389-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="10389-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10389-109">要求</span><span class="sxs-lookup"><span data-stu-id="10389-109">Requirements</span></span>  
 <span data-ttu-id="10389-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10389-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10389-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10389-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10389-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10389-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10389-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10389-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10389-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="10389-114">See also</span></span>

- [<span data-ttu-id="10389-115">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="10389-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="10389-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="10389-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
