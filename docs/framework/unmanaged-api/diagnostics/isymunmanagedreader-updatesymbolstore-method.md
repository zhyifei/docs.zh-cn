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
ms.openlocfilehash: ccc787aa1c820a486d9a513055c9c9834b90bd1a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615431"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="ba45d-102">ISymUnmanagedReader::UpdateSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="ba45d-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="ba45d-103">使用增量符号存储区更新现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="ba45d-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="ba45d-104">此方法在 "编辑并继续" 方案中用于更新符号存储区，以匹配原始可移植可执行（PE）文件的增量。</span><span class="sxs-lookup"><span data-stu-id="ba45d-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba45d-105">只需指定 `filename` 或 `pIStream` 参数之一，而不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ba45d-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="ba45d-106">如果 `filename` 指定了，则将用该文件中的符号更新符号存储区。</span><span class="sxs-lookup"><span data-stu-id="ba45d-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="ba45d-107">如果 `pIStream` 指定了，则将用中的数据更新存储区 <xref:System.Runtime.InteropServices.ComTypes.IStream> 。</span><span class="sxs-lookup"><span data-stu-id="ba45d-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba45d-108">语法</span><span class="sxs-lookup"><span data-stu-id="ba45d-108">Syntax</span></span>  
  
```cpp  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba45d-109">参数</span><span class="sxs-lookup"><span data-stu-id="ba45d-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="ba45d-110">中包含符号存储区的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ba45d-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="ba45d-111">中文件流，用作参数的替代项 `filename` 。</span><span class="sxs-lookup"><span data-stu-id="ba45d-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba45d-112">返回值</span><span class="sxs-lookup"><span data-stu-id="ba45d-112">Return Value</span></span>  
 <span data-ttu-id="ba45d-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="ba45d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba45d-114">要求</span><span class="sxs-lookup"><span data-stu-id="ba45d-114">Requirements</span></span>  
 <span data-ttu-id="ba45d-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="ba45d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba45d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba45d-116">See also</span></span>

- [<span data-ttu-id="ba45d-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="ba45d-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
