---
title: ICorDebugDataTarget2::GetImageLocation 方法
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: ba1cc8c91c53547c6ed4025ee67a69e253f3596d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783585"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="00217-102">ICorDebugDataTarget2::GetImageLocation 方法</span><span class="sxs-lookup"><span data-stu-id="00217-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="00217-103">返回模块基址中的模块路径。</span><span class="sxs-lookup"><span data-stu-id="00217-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00217-104">语法</span><span class="sxs-lookup"><span data-stu-id="00217-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00217-105">参数</span><span class="sxs-lookup"><span data-stu-id="00217-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="00217-106">中一个[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值表示模块的基址。</span><span class="sxs-lookup"><span data-stu-id="00217-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="00217-107">[输入] 缓冲器中将接收模块路径的字符数。</span><span class="sxs-lookup"><span data-stu-id="00217-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="00217-108">[输出] 指针指向写入 `szName` 缓冲器的字符数。</span><span class="sxs-lookup"><span data-stu-id="00217-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="00217-109">[输出] 模块路径。</span><span class="sxs-lookup"><span data-stu-id="00217-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00217-110">备注</span><span class="sxs-lookup"><span data-stu-id="00217-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00217-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="00217-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00217-112">需求</span><span class="sxs-lookup"><span data-stu-id="00217-112">Requirements</span></span>  
 <span data-ttu-id="00217-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00217-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00217-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00217-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00217-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00217-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00217-116">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00217-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00217-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00217-117">See also</span></span>

- [<span data-ttu-id="00217-118">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="00217-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="00217-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="00217-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
