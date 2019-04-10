---
title: ICorDebugStaticFieldSymbol::GetAddress 方法
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e233fe78f6b2c721114f0307a8ca414625a0087e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160415"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="11fbb-102">ICorDebugStaticFieldSymbol::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="11fbb-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="11fbb-103">获取静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="11fbb-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11fbb-104">语法</span><span class="sxs-lookup"><span data-stu-id="11fbb-104">Syntax</span></span>  
  
```  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11fbb-105">参数</span><span class="sxs-lookup"><span data-stu-id="11fbb-105">Parameters</span></span>  
 <span data-ttu-id="11fbb-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="11fbb-106">pRVA</span></span>  
 <span data-ttu-id="11fbb-107">[out] 指向静态字段的相对虚拟地址 (RVA) 的指针。</span><span class="sxs-lookup"><span data-stu-id="11fbb-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11fbb-108">备注</span><span class="sxs-lookup"><span data-stu-id="11fbb-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11fbb-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="11fbb-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11fbb-110">要求</span><span class="sxs-lookup"><span data-stu-id="11fbb-110">Requirements</span></span>  
 <span data-ttu-id="11fbb-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11fbb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11fbb-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11fbb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11fbb-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11fbb-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="11fbb-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="11fbb-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11fbb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="11fbb-115">See also</span></span>

- [<span data-ttu-id="11fbb-116">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="11fbb-116">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="11fbb-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="11fbb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
