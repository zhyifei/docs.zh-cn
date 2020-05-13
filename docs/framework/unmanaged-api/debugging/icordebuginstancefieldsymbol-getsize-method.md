---
title: ICorDebugInstanceFieldSymbol::GetSize 方法
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 3d3c6881ecd54fc48be92e5ea0dc74a5cfdabd8f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209947"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="2ae1c-102">ICorDebugInstanceFieldSymbol::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="2ae1c-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="2ae1c-103">获取实例字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2ae1c-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae1c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2ae1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ae1c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2ae1c-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="2ae1c-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="2ae1c-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ae1c-107">备注</span><span class="sxs-lookup"><span data-stu-id="2ae1c-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ae1c-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="2ae1c-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ae1c-109">要求</span><span class="sxs-lookup"><span data-stu-id="2ae1c-109">Requirements</span></span>  
 <span data-ttu-id="2ae1c-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2ae1c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ae1c-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ae1c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ae1c-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ae1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ae1c-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ae1c-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae1c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ae1c-114">See also</span></span>

- [<span data-ttu-id="2ae1c-115">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="2ae1c-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="2ae1c-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="2ae1c-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
