---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f7859b095d80edb5592af1386457ad72b85bc48
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957387"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="a99d3-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法</span><span class="sxs-lookup"><span data-stu-id="a99d3-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="a99d3-103">获取所有合并程序集的符号记录。</span><span class="sxs-lookup"><span data-stu-id="a99d3-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a99d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="a99d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a99d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="a99d3-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="a99d3-106">[in] 请求的符号记录数。</span><span class="sxs-lookup"><span data-stu-id="a99d3-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="a99d3-107">[out] 指向由方法检索的符号记录数的指针。</span><span class="sxs-lookup"><span data-stu-id="a99d3-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="a99d3-108">指向[ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)对象数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a99d3-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a99d3-109">备注</span><span class="sxs-lookup"><span data-stu-id="a99d3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a99d3-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a99d3-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a99d3-111">要求</span><span class="sxs-lookup"><span data-stu-id="a99d3-111">Requirements</span></span>  
 <span data-ttu-id="a99d3-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a99d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a99d3-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="a99d3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a99d3-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a99d3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a99d3-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a99d3-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a99d3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a99d3-116">See also</span></span>

- [<span data-ttu-id="a99d3-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="a99d3-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a99d3-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a99d3-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
