---
title: ICorDebugVariableSymbol::GetSlotIndex 方法
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 251a978e96ff396d0d9d9282ded7f8a25ae0ba0b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397082"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="b2106-102">ICorDebugVariableSymbol::GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="b2106-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="b2106-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="b2106-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2106-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2106-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2106-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2106-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="b2106-106">[out] 指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="b2106-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2106-107">返回值</span><span class="sxs-lookup"><span data-stu-id="b2106-107">Return Value</span></span>  
 <span data-ttu-id="b2106-108">`S_OK` 如果成功。</span><span class="sxs-lookup"><span data-stu-id="b2106-108">`S_OK` if successful.</span></span> <span data-ttu-id="b2106-109">如果变量是一个函数自变量，则为 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="b2106-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2106-110">备注</span><span class="sxs-lookup"><span data-stu-id="b2106-110">Remarks</span></span>  
 <span data-ttu-id="b2106-111">本地变量的托管槽索引可用于检索变量的元数据信息</span><span class="sxs-lookup"><span data-stu-id="b2106-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2106-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b2106-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2106-113">要求</span><span class="sxs-lookup"><span data-stu-id="b2106-113">Requirements</span></span>  
 <span data-ttu-id="b2106-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2106-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2106-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2106-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2106-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2106-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2106-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2106-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2106-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2106-118">See also</span></span>

- [<span data-ttu-id="b2106-119">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="b2106-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="b2106-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="b2106-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
