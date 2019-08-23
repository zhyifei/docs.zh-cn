---
title: ICorDebugInstanceFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ff0ddc266ef9a3f5fabf56f43f1eba2c74e3a8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910173"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="5d167-102">ICorDebugInstanceFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="5d167-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="5d167-103">获取实例字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5d167-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d167-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d167-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d167-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d167-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="5d167-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="5d167-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d167-107">备注</span><span class="sxs-lookup"><span data-stu-id="5d167-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d167-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="5d167-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d167-109">要求</span><span class="sxs-lookup"><span data-stu-id="5d167-109">Requirements</span></span>  
 <span data-ttu-id="5d167-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d167-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d167-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="5d167-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d167-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d167-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d167-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d167-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d167-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d167-114">See also</span></span>

- [<span data-ttu-id="5d167-115">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="5d167-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="5d167-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="5d167-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
