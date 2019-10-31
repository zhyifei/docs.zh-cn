---
title: ICorDebugSymbolProvider：： GetAssemblyImageBytes 方法
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 3184ba116704df8945b53766e62435a4252eaa11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138936"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="14a02-102">ICorDebugSymbolProvider：： GetAssemblyImageBytes 方法</span><span class="sxs-lookup"><span data-stu-id="14a02-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="14a02-103">给定合并程序集的相对虚拟地址 (RVA)，读取合并程序集中的数据。</span><span class="sxs-lookup"><span data-stu-id="14a02-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a02-104">语法</span><span class="sxs-lookup"><span data-stu-id="14a02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14a02-105">参数</span><span class="sxs-lookup"><span data-stu-id="14a02-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="14a02-106">[in] 合并程序集中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="14a02-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="14a02-107">要在合并程序集中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="14a02-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="14a02-108">指向[ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)对象地址的指针，该对象包含包含合并的程序集元数据的内存缓冲区的相关信息。</span><span class="sxs-lookup"><span data-stu-id="14a02-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14a02-109">备注</span><span class="sxs-lookup"><span data-stu-id="14a02-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14a02-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="14a02-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14a02-111">要求</span><span class="sxs-lookup"><span data-stu-id="14a02-111">Requirements</span></span>  
 <span data-ttu-id="14a02-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="14a02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14a02-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14a02-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14a02-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14a02-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14a02-115">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14a02-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a02-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="14a02-116">See also</span></span>

- [<span data-ttu-id="14a02-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="14a02-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="14a02-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="14a02-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
