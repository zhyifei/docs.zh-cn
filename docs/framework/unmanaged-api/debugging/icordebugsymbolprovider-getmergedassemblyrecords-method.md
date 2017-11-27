---
title: "ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f7515479ae5fbe490496bac79f102b02700dcee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="2c1fc-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法</span><span class="sxs-lookup"><span data-stu-id="2c1fc-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="2c1fc-103">获取所有合并程序集的符号记录。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c1fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c1fc-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c1fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c1fc-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="2c1fc-106">[in] 请求的符号记录数。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="2c1fc-107">[out] 指向由方法检索的符号记录数的指针。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="2c1fc-108">指向数组的指针[ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c1fc-109">备注</span><span class="sxs-lookup"><span data-stu-id="2c1fc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c1fc-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c1fc-111">要求</span><span class="sxs-lookup"><span data-stu-id="2c1fc-111">Requirements</span></span>  
 <span data-ttu-id="2c1fc-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c1fc-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c1fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c1fc-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c1fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c1fc-115">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c1fc-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1fc-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c1fc-116">See Also</span></span>  
 [<span data-ttu-id="2c1fc-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="2c1fc-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="2c1fc-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="2c1fc-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
