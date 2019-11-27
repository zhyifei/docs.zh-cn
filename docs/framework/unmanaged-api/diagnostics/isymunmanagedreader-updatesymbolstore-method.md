---
title: ISymUnmanagedReader::UpdateSymbolStore 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: e052d9b7b2abd57b176dfe3b00afac626d422c58
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446457"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="2f35a-102">ISymUnmanagedReader::UpdateSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="2f35a-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="2f35a-103">使用增量符号存储区更新现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="2f35a-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="2f35a-104">此方法在 "编辑并继续" 方案中用于更新符号存储区，以匹配原始可移植可执行（PE）文件的增量。</span><span class="sxs-lookup"><span data-stu-id="2f35a-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f35a-105">只需指定 `filename` 或 `pIStream` 参数之一，而不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="2f35a-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="2f35a-106">如果指定 `filename`，则将用该文件中的符号更新符号存储区。</span><span class="sxs-lookup"><span data-stu-id="2f35a-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="2f35a-107">如果指定 `pIStream`，则将用 <xref:System.Runtime.InteropServices.ComTypes.IStream>中的数据更新存储。</span><span class="sxs-lookup"><span data-stu-id="2f35a-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f35a-108">语法</span><span class="sxs-lookup"><span data-stu-id="2f35a-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f35a-109">参数</span><span class="sxs-lookup"><span data-stu-id="2f35a-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="2f35a-110">中包含符号存储区的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2f35a-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="2f35a-111">中用于作为 `filename` 参数的替代项的文件流。</span><span class="sxs-lookup"><span data-stu-id="2f35a-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f35a-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2f35a-112">Return Value</span></span>  
 <span data-ttu-id="2f35a-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="2f35a-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f35a-114">要求</span><span class="sxs-lookup"><span data-stu-id="2f35a-114">Requirements</span></span>  
 <span data-ttu-id="2f35a-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2f35a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f35a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f35a-116">See also</span></span>

- [<span data-ttu-id="2f35a-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="2f35a-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
