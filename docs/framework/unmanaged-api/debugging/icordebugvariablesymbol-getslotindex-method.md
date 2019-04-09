---
title: ICorDebugVariableSymbol::GetSlotIndex 方法
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: affe67006c9e37d55b0f9d107c92441da44c9ab8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138783"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="179da-102">ICorDebugVariableSymbol::GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="179da-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="179da-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="179da-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="179da-104">语法</span><span class="sxs-lookup"><span data-stu-id="179da-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="179da-105">参数</span><span class="sxs-lookup"><span data-stu-id="179da-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="179da-106">[out] 指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="179da-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="179da-107">返回值</span><span class="sxs-lookup"><span data-stu-id="179da-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="179da-108">如果成功。</span><span class="sxs-lookup"><span data-stu-id="179da-108">if successful.</span></span> `E_FAIL` <span data-ttu-id="179da-109">如果变量是函数的参数。</span><span class="sxs-lookup"><span data-stu-id="179da-109">if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="179da-110">备注</span><span class="sxs-lookup"><span data-stu-id="179da-110">Remarks</span></span>  
 <span data-ttu-id="179da-111">本地变量的托管槽索引可用于检索变量的元数据信息</span><span class="sxs-lookup"><span data-stu-id="179da-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="179da-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="179da-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="179da-113">要求</span><span class="sxs-lookup"><span data-stu-id="179da-113">Requirements</span></span>  
 <span data-ttu-id="179da-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="179da-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="179da-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="179da-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="179da-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="179da-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="179da-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="179da-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="179da-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="179da-118">See also</span></span>

- [<span data-ttu-id="179da-119">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="179da-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="179da-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="179da-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
