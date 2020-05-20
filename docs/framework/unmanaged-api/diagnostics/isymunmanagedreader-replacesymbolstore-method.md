---
title: ISymUnmanagedReader::ReplaceSymbolStore 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
ms.openlocfilehash: db2137146ded5200e05bbf88e23ae599f3eb7dec
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615444"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="071c4-102">ISymUnmanagedReader::ReplaceSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="071c4-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="071c4-103">用增量符号存储区替换现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="071c4-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="071c4-104">此方法类似于[UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md)方法，不同之处在于给定增量充当完全替换而不是更新。</span><span class="sxs-lookup"><span data-stu-id="071c4-104">This method is similar to the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="071c4-105">只需指定 `filename` 或 `pIStream` 参数之一，而不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="071c4-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="071c4-106">如果 `filename` 指定了，则将用该文件中的符号更新符号存储区。</span><span class="sxs-lookup"><span data-stu-id="071c4-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="071c4-107">如果 `pIStream` 指定了，则将用中的数据更新存储区 <xref:System.Runtime.InteropServices.ComTypes.IStream> 。</span><span class="sxs-lookup"><span data-stu-id="071c4-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="071c4-108">语法</span><span class="sxs-lookup"><span data-stu-id="071c4-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="071c4-109">参数</span><span class="sxs-lookup"><span data-stu-id="071c4-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="071c4-110">中包含符号存储区的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="071c4-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="071c4-111">中文件流，用作参数的替代项 `filename` 。</span><span class="sxs-lookup"><span data-stu-id="071c4-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="071c4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="071c4-112">Return Value</span></span>  
 <span data-ttu-id="071c4-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="071c4-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="071c4-114">要求</span><span class="sxs-lookup"><span data-stu-id="071c4-114">Requirements</span></span>  
 <span data-ttu-id="071c4-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="071c4-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="071c4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="071c4-116">See also</span></span>

- [<span data-ttu-id="071c4-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="071c4-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
