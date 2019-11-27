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
ms.openlocfilehash: 60c3537a80c39f758f46e6f2f0a5f2bcd27350b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445733"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="6030e-102">ISymUnmanagedReader::ReplaceSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="6030e-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="6030e-103">用增量符号存储区替换现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="6030e-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="6030e-104">此方法类似于[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法，不同之处在于给定增量充当完全替换而不是更新。</span><span class="sxs-lookup"><span data-stu-id="6030e-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6030e-105">只需指定 `filename` 或 `pIStream` 参数之一，而不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="6030e-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="6030e-106">如果指定 `filename`，则将用该文件中的符号更新符号存储区。</span><span class="sxs-lookup"><span data-stu-id="6030e-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="6030e-107">如果指定 `pIStream`，则将用 <xref:System.Runtime.InteropServices.ComTypes.IStream>中的数据更新存储。</span><span class="sxs-lookup"><span data-stu-id="6030e-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6030e-108">语法</span><span class="sxs-lookup"><span data-stu-id="6030e-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6030e-109">参数</span><span class="sxs-lookup"><span data-stu-id="6030e-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="6030e-110">中包含符号存储区的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6030e-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="6030e-111">中用于作为 `filename` 参数的替代项的文件流。</span><span class="sxs-lookup"><span data-stu-id="6030e-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6030e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6030e-112">Return Value</span></span>  
 <span data-ttu-id="6030e-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="6030e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6030e-114">要求</span><span class="sxs-lookup"><span data-stu-id="6030e-114">Requirements</span></span>  
 <span data-ttu-id="6030e-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="6030e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6030e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6030e-116">See also</span></span>

- [<span data-ttu-id="6030e-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="6030e-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
