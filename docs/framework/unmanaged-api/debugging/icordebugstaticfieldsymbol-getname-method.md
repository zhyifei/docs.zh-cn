---
title: ICorDebugStaticFieldSymbol::GetName 方法
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffcd6971a3229423f055765b0d64258a2dfa2aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477929"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="a189c-102">ICorDebugStaticFieldSymbol::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="a189c-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="a189c-103">获取静态字段的名称。</span><span class="sxs-lookup"><span data-stu-id="a189c-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a189c-104">语法</span><span class="sxs-lookup"><span data-stu-id="a189c-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a189c-105">参数</span><span class="sxs-lookup"><span data-stu-id="a189c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a189c-106">[in] `szName` 缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="a189c-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a189c-107">[out] 指向实际写入 `szName` 缓冲区的字符数。缓冲区的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="a189c-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a189c-108">[out] 用于存储返回名称的字符数组。</span><span class="sxs-lookup"><span data-stu-id="a189c-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a189c-109">备注</span><span class="sxs-lookup"><span data-stu-id="a189c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a189c-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a189c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a189c-111">要求</span><span class="sxs-lookup"><span data-stu-id="a189c-111">Requirements</span></span>  
 <span data-ttu-id="a189c-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a189c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a189c-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a189c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a189c-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a189c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a189c-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a189c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a189c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a189c-116">See also</span></span>
- [<span data-ttu-id="a189c-117">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="a189c-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="a189c-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a189c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
