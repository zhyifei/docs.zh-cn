---
title: ICorDebugDataTarget2::GetImageFromPointer 方法
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64affd9b262934316fc904b10f1a9c4a7e7657bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539969"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="40825-102">ICorDebugDataTarget2::GetImageFromPointer 方法</span><span class="sxs-lookup"><span data-stu-id="40825-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="40825-103">返回该模块地址中的模块基址和大小。</span><span class="sxs-lookup"><span data-stu-id="40825-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40825-104">语法</span><span class="sxs-lookup"><span data-stu-id="40825-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40825-105">参数</span><span class="sxs-lookup"><span data-stu-id="40825-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="40825-106">一个[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值表示在模块中的地址。</span><span class="sxs-lookup"><span data-stu-id="40825-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="40825-107">[out]一个[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值表示模块的基址。</span><span class="sxs-lookup"><span data-stu-id="40825-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="40825-108">指针指向模块大小。</span><span class="sxs-lookup"><span data-stu-id="40825-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40825-109">备注</span><span class="sxs-lookup"><span data-stu-id="40825-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40825-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="40825-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40825-111">要求</span><span class="sxs-lookup"><span data-stu-id="40825-111">Requirements</span></span>  
 <span data-ttu-id="40825-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40825-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40825-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40825-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40825-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40825-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40825-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40825-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40825-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="40825-116">See also</span></span>
- [<span data-ttu-id="40825-117">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="40825-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="40825-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="40825-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
