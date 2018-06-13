---
title: ICorDebugDataTarget2::GetImageLocation 方法
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6962c8063479b3b0279d771b1b0cd1df63f696b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416411"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="b95b0-102">ICorDebugDataTarget2::GetImageLocation 方法</span><span class="sxs-lookup"><span data-stu-id="b95b0-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="b95b0-103">返回模块基址中的模块路径。</span><span class="sxs-lookup"><span data-stu-id="b95b0-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b95b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="b95b0-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b95b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="b95b0-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="b95b0-106">[in]A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)表示模块的基址的值。</span><span class="sxs-lookup"><span data-stu-id="b95b0-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b95b0-107">[输入] 缓冲器中将接收模块路径的字符数。</span><span class="sxs-lookup"><span data-stu-id="b95b0-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b95b0-108">[输出] 指针指向写入 `szName` 缓冲器的字符数。</span><span class="sxs-lookup"><span data-stu-id="b95b0-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="b95b0-109">[输出] 模块路径。</span><span class="sxs-lookup"><span data-stu-id="b95b0-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b95b0-110">备注</span><span class="sxs-lookup"><span data-stu-id="b95b0-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b95b0-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="b95b0-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b95b0-112">要求</span><span class="sxs-lookup"><span data-stu-id="b95b0-112">Requirements</span></span>  
 <span data-ttu-id="b95b0-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b95b0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b95b0-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b95b0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b95b0-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b95b0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b95b0-116">**.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b95b0-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b95b0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b95b0-117">See Also</span></span>  
 [<span data-ttu-id="b95b0-118">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="b95b0-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="b95b0-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="b95b0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
