---
title: ICorDebugDataTarget2::GetSymbolProviderForImage 方法
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e5a6e70d5148756a5ed8d17c56577da920d1b69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911453"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="13129-102">ICorDebugDataTarget2::GetSymbolProviderForImage 方法</span><span class="sxs-lookup"><span data-stu-id="13129-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="13129-103">返回该模块基址中的模块符号提供程序。</span><span class="sxs-lookup"><span data-stu-id="13129-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13129-104">语法</span><span class="sxs-lookup"><span data-stu-id="13129-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13129-105">参数</span><span class="sxs-lookup"><span data-stu-id="13129-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="13129-106">中一个[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值, 该值表示模块的基址。</span><span class="sxs-lookup"><span data-stu-id="13129-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="13129-107">弄指向[ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="13129-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13129-108">备注</span><span class="sxs-lookup"><span data-stu-id="13129-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="13129-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="13129-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13129-110">要求</span><span class="sxs-lookup"><span data-stu-id="13129-110">Requirements</span></span>  
 <span data-ttu-id="13129-111">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13129-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13129-112">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="13129-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13129-113">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13129-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13129-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13129-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13129-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="13129-115">See also</span></span>

- [<span data-ttu-id="13129-116">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="13129-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="13129-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="13129-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
