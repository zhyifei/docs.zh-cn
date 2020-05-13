---
title: ICorDebugLoadedModule::GetSize 方法
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 6a1c8c94b3c45ac995501b84bb4a69d73e7db25b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209846"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="017f8-102">ICorDebugLoadedModule::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="017f8-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="017f8-103">获取加载模块的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="017f8-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="017f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="017f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="017f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="017f8-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="017f8-106">[out] 指向已加载模块中字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="017f8-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="017f8-107">备注</span><span class="sxs-lookup"><span data-stu-id="017f8-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="017f8-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="017f8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="017f8-109">要求</span><span class="sxs-lookup"><span data-stu-id="017f8-109">Requirements</span></span>  
 <span data-ttu-id="017f8-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="017f8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="017f8-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="017f8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="017f8-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="017f8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="017f8-113">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="017f8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017f8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="017f8-114">See also</span></span>

- [<span data-ttu-id="017f8-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="017f8-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="017f8-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="017f8-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
