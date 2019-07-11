---
title: 'Icordebugvariablesymbol:: Getsize 方法'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e963e655c933c9191953bb32ba0b73adf0ae86d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774868"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="7d570-102">Icordebugvariablesymbol:: Getsize 方法</span><span class="sxs-lookup"><span data-stu-id="7d570-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="7d570-103">获取变量的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7d570-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d570-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d570-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d570-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d570-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="7d570-106">指向包含变量大小的 32 位无符号整数的指针。</span><span class="sxs-lookup"><span data-stu-id="7d570-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d570-107">备注</span><span class="sxs-lookup"><span data-stu-id="7d570-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d570-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="7d570-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d570-109">要求</span><span class="sxs-lookup"><span data-stu-id="7d570-109">Requirements</span></span>  
 <span data-ttu-id="7d570-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d570-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d570-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d570-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d570-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d570-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d570-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d570-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d570-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d570-114">See also</span></span>

- [<span data-ttu-id="7d570-115">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="7d570-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="7d570-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="7d570-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
