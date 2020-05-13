---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: b7d26fa80a7a8ebe7b4606b914c8cd09c52df1e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379626"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="61e56-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords 方法</span><span class="sxs-lookup"><span data-stu-id="61e56-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="61e56-103">获取所有合并程序集的符号记录。</span><span class="sxs-lookup"><span data-stu-id="61e56-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61e56-104">语法</span><span class="sxs-lookup"><span data-stu-id="61e56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61e56-105">参数</span><span class="sxs-lookup"><span data-stu-id="61e56-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="61e56-106">[in] 请求的符号记录数。</span><span class="sxs-lookup"><span data-stu-id="61e56-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="61e56-107">[out] 指向由方法检索的符号记录数的指针。</span><span class="sxs-lookup"><span data-stu-id="61e56-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="61e56-108">指向[ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)对象数组的指针。</span><span class="sxs-lookup"><span data-stu-id="61e56-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61e56-109">备注</span><span class="sxs-lookup"><span data-stu-id="61e56-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="61e56-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="61e56-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61e56-111">要求</span><span class="sxs-lookup"><span data-stu-id="61e56-111">Requirements</span></span>  
 <span data-ttu-id="61e56-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61e56-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61e56-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61e56-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61e56-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61e56-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61e56-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61e56-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e56-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="61e56-116">See also</span></span>

- [<span data-ttu-id="61e56-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="61e56-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="61e56-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="61e56-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
