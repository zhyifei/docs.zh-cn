---
title: ICorDebugMergedAssemblyRecord::GetIndex 方法
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca304b90cee291ef86e225c2b0691631833e53a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917945"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="f8e67-102">ICorDebugMergedAssemblyRecord::GetIndex 方法</span><span class="sxs-lookup"><span data-stu-id="f8e67-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="f8e67-103">获取程序集的前缀索引。</span><span class="sxs-lookup"><span data-stu-id="f8e67-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e67-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8e67-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8e67-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8e67-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="f8e67-106">[out] 指向前缀索引的指针。</span><span class="sxs-lookup"><span data-stu-id="f8e67-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8e67-107">备注</span><span class="sxs-lookup"><span data-stu-id="f8e67-107">Remarks</span></span>  
 <span data-ttu-id="f8e67-108">前缀索引用于防止合并的元数据类型名称出现名称冲突。</span><span class="sxs-lookup"><span data-stu-id="f8e67-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8e67-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f8e67-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8e67-110">要求</span><span class="sxs-lookup"><span data-stu-id="f8e67-110">Requirements</span></span>  
 <span data-ttu-id="f8e67-111">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8e67-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8e67-112">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="f8e67-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8e67-113">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8e67-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8e67-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e67-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e67-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8e67-115">See also</span></span>

- [<span data-ttu-id="f8e67-116">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="f8e67-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f8e67-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="f8e67-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
