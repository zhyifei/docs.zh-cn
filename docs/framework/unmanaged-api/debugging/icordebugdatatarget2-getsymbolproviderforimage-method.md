---
title: ICorDebugDataTarget2::GetSymbolProviderForImage 方法
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 500d36b414be686071990a6e1b40dd8759d02ae9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178931"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="1909a-102">ICorDebugDataTarget2::GetSymbolProviderForImage 方法</span><span class="sxs-lookup"><span data-stu-id="1909a-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="1909a-103">返回该模块基址中的模块符号提供程序。</span><span class="sxs-lookup"><span data-stu-id="1909a-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1909a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1909a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1909a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="1909a-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="1909a-106">[在]表示模块基本地址的[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值。</span><span class="sxs-lookup"><span data-stu-id="1909a-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="1909a-107">[出]指向[ICorDebugSymbol 提供程序](icordebugsymbolprovider-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="1909a-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1909a-108">备注</span><span class="sxs-lookup"><span data-stu-id="1909a-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1909a-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="1909a-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1909a-110">要求</span><span class="sxs-lookup"><span data-stu-id="1909a-110">Requirements</span></span>  
 <span data-ttu-id="1909a-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1909a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1909a-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1909a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1909a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1909a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1909a-114">**.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1909a-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1909a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1909a-115">See also</span></span>

- [<span data-ttu-id="1909a-116">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="1909a-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="1909a-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="1909a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
