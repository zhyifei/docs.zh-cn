---
title: 'ICorDebugVariableSymbol:: GetSize 方法'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 782073968030d3dcdbbe49e0ed7732fe15c4a3bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968168"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="a4290-102">ICorDebugVariableSymbol:: GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="a4290-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="a4290-103">获取变量的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a4290-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4290-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4290-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4290-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4290-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="a4290-106">指向包含变量大小的 32 位无符号整数的指针。</span><span class="sxs-lookup"><span data-stu-id="a4290-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4290-107">备注</span><span class="sxs-lookup"><span data-stu-id="a4290-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4290-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a4290-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4290-109">要求</span><span class="sxs-lookup"><span data-stu-id="a4290-109">Requirements</span></span>  
 <span data-ttu-id="a4290-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4290-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4290-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="a4290-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4290-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4290-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4290-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4290-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4290-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4290-114">See also</span></span>

- [<span data-ttu-id="a4290-115">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="a4290-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="a4290-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="a4290-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
