---
title: "ICorDebugDataTarget2::GetImageLocation 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d35e35ecf4dfc62575e42a45a861ad685f3f26b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="863b4-102">ICorDebugDataTarget2::GetImageLocation 方法</span><span class="sxs-lookup"><span data-stu-id="863b4-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="863b4-103">返回模块基址中的模块路径。</span><span class="sxs-lookup"><span data-stu-id="863b4-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="863b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="863b4-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="863b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="863b4-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="863b4-106">[in]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)表示模块的基址的值。</span><span class="sxs-lookup"><span data-stu-id="863b4-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="863b4-107">[输入] 缓冲器中将接收模块路径的字符数。</span><span class="sxs-lookup"><span data-stu-id="863b4-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="863b4-108">[输出] 指针指向写入 `szName` 缓冲器的字符数。</span><span class="sxs-lookup"><span data-stu-id="863b4-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="863b4-109">[输出] 模块路径。</span><span class="sxs-lookup"><span data-stu-id="863b4-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="863b4-110">备注</span><span class="sxs-lookup"><span data-stu-id="863b4-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="863b4-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="863b4-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="863b4-112">要求</span><span class="sxs-lookup"><span data-stu-id="863b4-112">Requirements</span></span>  
 <span data-ttu-id="863b4-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="863b4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="863b4-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="863b4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="863b4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="863b4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="863b4-116">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="863b4-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="863b4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="863b4-117">See Also</span></span>  
 [<span data-ttu-id="863b4-118">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="863b4-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="863b4-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="863b4-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
