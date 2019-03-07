---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes 方法
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c44260d3b5baa18bc24f85cdbea94016b43291e2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489778"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="f8f21-102">ICorDebugSymbolProvider::GetAssemblyImageBytes 方法</span><span class="sxs-lookup"><span data-stu-id="f8f21-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="f8f21-103">给定合并程序集的相对虚拟地址 (RVA)，读取合并程序集中的数据。</span><span class="sxs-lookup"><span data-stu-id="f8f21-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f21-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8f21-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8f21-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8f21-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="f8f21-106">[in] 合并程序集中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="f8f21-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="f8f21-107">要在合并程序集中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="f8f21-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="f8f21-108">指向的地址的指针[ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)对象，其中包含有关与合并程序集元数据的内存缓冲区的信息。</span><span class="sxs-lookup"><span data-stu-id="f8f21-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8f21-109">备注</span><span class="sxs-lookup"><span data-stu-id="f8f21-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8f21-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f8f21-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f21-111">要求</span><span class="sxs-lookup"><span data-stu-id="f8f21-111">Requirements</span></span>  
 <span data-ttu-id="f8f21-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f21-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8f21-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8f21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8f21-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8f21-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8f21-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8f21-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f21-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8f21-116">See also</span></span>
- [<span data-ttu-id="f8f21-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="f8f21-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f8f21-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="f8f21-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
