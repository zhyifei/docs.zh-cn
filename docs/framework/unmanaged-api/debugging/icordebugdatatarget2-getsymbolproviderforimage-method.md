---
title: ICorDebugDataTarget2::GetSymbolProviderForImage 方法
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: bada60295c3a9b3a702aa674e06f8f5cf6ac0a24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788824"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="6eea6-102">ICorDebugDataTarget2::GetSymbolProviderForImage 方法</span><span class="sxs-lookup"><span data-stu-id="6eea6-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="6eea6-103">返回该模块基址中的模块符号提供程序。</span><span class="sxs-lookup"><span data-stu-id="6eea6-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eea6-104">语法</span><span class="sxs-lookup"><span data-stu-id="6eea6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6eea6-105">参数</span><span class="sxs-lookup"><span data-stu-id="6eea6-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="6eea6-106">中一个[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值表示模块的基址。</span><span class="sxs-lookup"><span data-stu-id="6eea6-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="6eea6-107">弄指向[ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6eea6-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eea6-108">备注</span><span class="sxs-lookup"><span data-stu-id="6eea6-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6eea6-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="6eea6-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eea6-110">需求</span><span class="sxs-lookup"><span data-stu-id="6eea6-110">Requirements</span></span>  
 <span data-ttu-id="6eea6-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6eea6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eea6-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6eea6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eea6-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eea6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eea6-114">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eea6-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eea6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6eea6-115">See also</span></span>

- [<span data-ttu-id="6eea6-116">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="6eea6-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="6eea6-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="6eea6-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
