---
title: ICorDebugVariableSymbol::GetSlotIndex 方法
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58bb2cc63f2336ca9cfbed8ebeac0d607c18b2c4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968162"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="c222c-102">ICorDebugVariableSymbol::GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="c222c-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="c222c-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="c222c-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c222c-104">语法</span><span class="sxs-lookup"><span data-stu-id="c222c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c222c-105">参数</span><span class="sxs-lookup"><span data-stu-id="c222c-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="c222c-106">[out] 指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="c222c-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c222c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c222c-107">Return Value</span></span>  
 <span data-ttu-id="c222c-108">`S_OK` 如果成功。</span><span class="sxs-lookup"><span data-stu-id="c222c-108">`S_OK` if successful.</span></span> <span data-ttu-id="c222c-109">如果变量是一个函数自变量，则为 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="c222c-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c222c-110">备注</span><span class="sxs-lookup"><span data-stu-id="c222c-110">Remarks</span></span>  
 <span data-ttu-id="c222c-111">本地变量的托管槽索引可用于检索变量的元数据信息</span><span class="sxs-lookup"><span data-stu-id="c222c-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c222c-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c222c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c222c-113">要求</span><span class="sxs-lookup"><span data-stu-id="c222c-113">Requirements</span></span>  
 <span data-ttu-id="c222c-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c222c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c222c-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="c222c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c222c-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c222c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c222c-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c222c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c222c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c222c-118">See also</span></span>

- [<span data-ttu-id="c222c-119">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="c222c-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="c222c-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="c222c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
