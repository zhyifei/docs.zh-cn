---
title: ICorDebugMergedAssemblyRecord::GetSimpleName 方法
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0919f0cfd0ae1617d140eadd12aa8874c73d8bb0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491645"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="a50bc-102">ICorDebugMergedAssemblyRecord::GetSimpleName 方法</span><span class="sxs-lookup"><span data-stu-id="a50bc-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="a50bc-103">获取程序集的简单名。</span><span class="sxs-lookup"><span data-stu-id="a50bc-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="a50bc-104">Syntax</span></span>  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a50bc-105">参数</span><span class="sxs-lookup"><span data-stu-id="a50bc-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a50bc-106">[in] `szName` 缓冲区中的字符数。</span><span class="sxs-lookup"><span data-stu-id="a50bc-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a50bc-107">[out] 指向实际写入 `szName` 缓冲区的字符数。缓冲区的字符数的指针。</span><span class="sxs-lookup"><span data-stu-id="a50bc-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a50bc-108">指向字符数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a50bc-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50bc-109">备注</span><span class="sxs-lookup"><span data-stu-id="a50bc-109">Remarks</span></span>  
 <span data-ttu-id="a50bc-110">此方法检索程序集的简单名（例如“System.Collections”），该名称不带文件扩展名、版本、区域性或公钥标记。</span><span class="sxs-lookup"><span data-stu-id="a50bc-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="a50bc-111">它对应托管代码中的 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="a50bc-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a50bc-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a50bc-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a50bc-113">要求</span><span class="sxs-lookup"><span data-stu-id="a50bc-113">Requirements</span></span>  
 <span data-ttu-id="a50bc-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a50bc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a50bc-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a50bc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a50bc-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a50bc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a50bc-117">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a50bc-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50bc-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a50bc-118">See also</span></span>
- [<span data-ttu-id="a50bc-119">ICorDebugMergedAssemblyRecord 接口</span><span class="sxs-lookup"><span data-stu-id="a50bc-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="a50bc-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="a50bc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
