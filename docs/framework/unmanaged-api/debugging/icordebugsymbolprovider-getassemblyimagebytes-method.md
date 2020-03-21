---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes 方法
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: 6361b12802876ef480acbe1cc13f32b77ba0be49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178492"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="c57f8-102">ICorDebugSymbolProvider::GetAssemblyImageBytes 方法</span><span class="sxs-lookup"><span data-stu-id="c57f8-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="c57f8-103">给定合并程序集的相对虚拟地址 (RVA)，读取合并程序集中的数据。</span><span class="sxs-lookup"><span data-stu-id="c57f8-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c57f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="c57f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c57f8-105">parameters</span><span class="sxs-lookup"><span data-stu-id="c57f8-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="c57f8-106">[in] 合并程序集中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="c57f8-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="c57f8-107">要在合并程序集中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="c57f8-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="c57f8-108">指向[ICorDebug记忆缓冲区](icordebugmemorybuffer-interface.md)对象的地址的指针，该对象包含有关具有合并程序集元数据的内存缓冲区的信息。</span><span class="sxs-lookup"><span data-stu-id="c57f8-108">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c57f8-109">备注</span><span class="sxs-lookup"><span data-stu-id="c57f8-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c57f8-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c57f8-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c57f8-111">要求</span><span class="sxs-lookup"><span data-stu-id="c57f8-111">Requirements</span></span>  
 <span data-ttu-id="c57f8-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c57f8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c57f8-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c57f8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c57f8-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c57f8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c57f8-115">**.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c57f8-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57f8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c57f8-116">See also</span></span>

- [<span data-ttu-id="c57f8-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="c57f8-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="c57f8-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="c57f8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
