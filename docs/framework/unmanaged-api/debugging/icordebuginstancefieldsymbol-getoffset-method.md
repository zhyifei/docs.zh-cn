---
title: ICorDebugInstanceFieldSymbol::GetName 方法
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: f7c13d397b39698bdf1a22f14820680e1fd0a25f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782288"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="9055f-102">ICorDebugInstanceFieldSymbol::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="9055f-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="9055f-103">获取父类中此示例字段的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="9055f-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9055f-104">语法</span><span class="sxs-lookup"><span data-stu-id="9055f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9055f-105">参数</span><span class="sxs-lookup"><span data-stu-id="9055f-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="9055f-106">指向此示例字段在父类中偏移的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="9055f-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9055f-107">备注</span><span class="sxs-lookup"><span data-stu-id="9055f-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9055f-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="9055f-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9055f-109">需求</span><span class="sxs-lookup"><span data-stu-id="9055f-109">Requirements</span></span>  
 <span data-ttu-id="9055f-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9055f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9055f-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9055f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9055f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9055f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9055f-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9055f-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9055f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9055f-114">See also</span></span>

- [<span data-ttu-id="9055f-115">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="9055f-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="9055f-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="9055f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
