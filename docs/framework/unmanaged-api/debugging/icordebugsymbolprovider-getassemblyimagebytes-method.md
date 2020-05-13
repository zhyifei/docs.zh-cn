---
title: ICorDebugSymbolProvider::GetAssemblyImageBytes 方法
ms.date: 03/30/2017
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
ms.openlocfilehash: a555acb9e23098b0a0f70924032771b1ae18e88e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376115"
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="a5034-102">ICorDebugSymbolProvider::GetAssemblyImageBytes 方法</span><span class="sxs-lookup"><span data-stu-id="a5034-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="a5034-103">给定合并程序集的相对虚拟地址 (RVA)，读取合并程序集中的数据。</span><span class="sxs-lookup"><span data-stu-id="a5034-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5034-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5034-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,
   [in] ULONG32 length,
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5034-105">参数</span><span class="sxs-lookup"><span data-stu-id="a5034-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="a5034-106">[in] 合并程序集中的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="a5034-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="a5034-107">要在合并程序集中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="a5034-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="a5034-108">指向[ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)对象地址的指针，该对象包含包含合并的程序集元数据的内存缓冲区的相关信息。</span><span class="sxs-lookup"><span data-stu-id="a5034-108">A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5034-109">备注</span><span class="sxs-lookup"><span data-stu-id="a5034-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5034-110">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a5034-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5034-111">要求</span><span class="sxs-lookup"><span data-stu-id="a5034-111">Requirements</span></span>  
 <span data-ttu-id="a5034-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5034-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5034-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5034-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5034-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5034-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5034-115">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5034-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5034-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5034-116">See also</span></span>

- [<span data-ttu-id="a5034-117">ICorDebugSymbolProvider 接口</span><span class="sxs-lookup"><span data-stu-id="a5034-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a5034-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="a5034-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
