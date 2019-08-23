---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes 方法
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf6e707b6176ccd205785aafa6c5a1adf0a3fc78
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964662"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="5a524-102">ICorDebugSymbolProvider::GetAssemblyImageBytes 方法</span><span class="sxs-lookup"><span data-stu-id="5a524-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="5a524-103">给定合并程序集的相对虚拟地址 (RVA)，读取合并程序集中的数据。</span><span class="sxs-lookup"><span data-stu-id="5a524-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a524-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a524-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a524-105">参数</span><span class="sxs-lookup"><span data-stu-id="5a524-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="5a524-106">[in] 合并程序集中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="5a524-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="5a524-107">要在合并程序集中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="5a524-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="5a524-108">指向[ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)对象地址的指针, 该对象包含包含合并的程序集元数据的内存缓冲区的相关信息。</span><span class="sxs-lookup"><span data-stu-id="5a524-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a524-109">备注</span><span class="sxs-lookup"><span data-stu-id="5a524-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a524-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="5a524-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a524-111">要求</span><span class="sxs-lookup"><span data-stu-id="5a524-111">Requirements</span></span>  
 <span data-ttu-id="5a524-112">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5a524-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a524-113">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="5a524-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a524-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a524-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a524-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a524-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a524-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a524-116">See also</span></span>

- [<span data-ttu-id="5a524-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="5a524-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5a524-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="5a524-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
