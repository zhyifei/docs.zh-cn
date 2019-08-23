---
title: ICorDebugInstanceFieldSymbol::GetName 方法
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b1b3cc489c504942806b043fa2e3b76d5415d84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936934"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="cb318-102">ICorDebugInstanceFieldSymbol::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="cb318-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="cb318-103">获取实例字段的名称。</span><span class="sxs-lookup"><span data-stu-id="cb318-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb318-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb318-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb318-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb318-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="cb318-106">[in] `szName` 缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="cb318-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cb318-107">[out] 指向实际写入 `szName` 缓冲区的字符数。缓冲区的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="cb318-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="cb318-108">[out] 用于存储返回名称的字符数组。</span><span class="sxs-lookup"><span data-stu-id="cb318-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb318-109">备注</span><span class="sxs-lookup"><span data-stu-id="cb318-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb318-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="cb318-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb318-111">要求</span><span class="sxs-lookup"><span data-stu-id="cb318-111">Requirements</span></span>  
 <span data-ttu-id="cb318-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb318-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb318-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="cb318-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb318-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb318-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb318-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb318-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb318-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb318-116">See also</span></span>

- [<span data-ttu-id="cb318-117">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="cb318-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="cb318-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="cb318-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
