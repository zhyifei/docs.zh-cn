---
title: ICorDebugVariableSymbol::GetSlotIndex 方法
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3510daffb55bdb22aa5f835bf27157e7c8428509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790897"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="65e5b-102">ICorDebugVariableSymbol::GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="65e5b-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="65e5b-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="65e5b-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65e5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="65e5b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65e5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="65e5b-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="65e5b-106">[out] 指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="65e5b-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65e5b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="65e5b-107">Return Value</span></span>  
 <span data-ttu-id="65e5b-108">`S_OK` 如果成功。</span><span class="sxs-lookup"><span data-stu-id="65e5b-108">`S_OK` if successful.</span></span> <span data-ttu-id="65e5b-109">如果变量是一个函数自变量，则为 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="65e5b-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65e5b-110">备注</span><span class="sxs-lookup"><span data-stu-id="65e5b-110">Remarks</span></span>  
 <span data-ttu-id="65e5b-111">本地变量的托管槽索引可用于检索变量的元数据信息</span><span class="sxs-lookup"><span data-stu-id="65e5b-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65e5b-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="65e5b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65e5b-113">需求</span><span class="sxs-lookup"><span data-stu-id="65e5b-113">Requirements</span></span>  
 <span data-ttu-id="65e5b-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="65e5b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65e5b-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65e5b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65e5b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65e5b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65e5b-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65e5b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65e5b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65e5b-118">See also</span></span>

- [<span data-ttu-id="65e5b-119">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="65e5b-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="65e5b-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="65e5b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
