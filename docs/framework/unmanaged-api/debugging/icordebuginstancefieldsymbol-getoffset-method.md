---
title: ICorDebugInstanceFieldSymbol::GetName 方法
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 453f691f414050905f5d73e201ebeed79e2aaf50
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910208"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="444ca-102">ICorDebugInstanceFieldSymbol::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="444ca-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="444ca-103">获取父类中此示例字段的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="444ca-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="444ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="444ca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="444ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="444ca-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="444ca-106">指向此示例字段在父类中偏移的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="444ca-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="444ca-107">备注</span><span class="sxs-lookup"><span data-stu-id="444ca-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="444ca-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="444ca-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="444ca-109">要求</span><span class="sxs-lookup"><span data-stu-id="444ca-109">Requirements</span></span>  
 <span data-ttu-id="444ca-110">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="444ca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="444ca-111">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="444ca-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="444ca-112">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="444ca-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="444ca-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="444ca-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="444ca-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="444ca-114">See also</span></span>

- [<span data-ttu-id="444ca-115">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="444ca-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="444ca-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="444ca-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
