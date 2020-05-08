---
title: ICorDebugDataTarget2::GetImageLocation 方法
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: 185b6a4979491a323f6eb15ab08a06f87fabc8d3
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976455"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="34fca-102">ICorDebugDataTarget2::GetImageLocation 方法</span><span class="sxs-lookup"><span data-stu-id="34fca-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="34fca-103">返回模块基址中的模块路径。</span><span class="sxs-lookup"><span data-stu-id="34fca-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34fca-104">语法</span><span class="sxs-lookup"><span data-stu-id="34fca-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34fca-105">参数</span><span class="sxs-lookup"><span data-stu-id="34fca-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="34fca-106">中一个[CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md)值，该值表示模块的基址。</span><span class="sxs-lookup"><span data-stu-id="34fca-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="34fca-107">[输入] 缓冲器中将接收模块路径的字符数。</span><span class="sxs-lookup"><span data-stu-id="34fca-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="34fca-108">[输出] 指针指向写入 `szName` 缓冲器的字符数。</span><span class="sxs-lookup"><span data-stu-id="34fca-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="34fca-109">[输出] 模块路径。</span><span class="sxs-lookup"><span data-stu-id="34fca-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34fca-110">备注</span><span class="sxs-lookup"><span data-stu-id="34fca-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34fca-111">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="34fca-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34fca-112">要求</span><span class="sxs-lookup"><span data-stu-id="34fca-112">Requirements</span></span>  
 <span data-ttu-id="34fca-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34fca-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34fca-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34fca-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34fca-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34fca-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34fca-116">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34fca-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34fca-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34fca-117">See also</span></span>

- [<span data-ttu-id="34fca-118">“ICor调试数据目标2”接口</span><span class="sxs-lookup"><span data-stu-id="34fca-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="34fca-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="34fca-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
