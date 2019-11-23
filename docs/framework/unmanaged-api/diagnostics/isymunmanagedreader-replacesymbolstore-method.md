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
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="d701b-102">ISymUnmanagedReader::ReplaceSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="d701b-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="d701b-103">用增量符号存储区替换现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="d701b-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="d701b-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span><span class="sxs-lookup"><span data-stu-id="d701b-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d701b-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span><span class="sxs-lookup"><span data-stu-id="d701b-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="d701b-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span><span class="sxs-lookup"><span data-stu-id="d701b-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="d701b-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span><span class="sxs-lookup"><span data-stu-id="d701b-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d701b-108">语法</span><span class="sxs-lookup"><span data-stu-id="d701b-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d701b-109">参数</span><span class="sxs-lookup"><span data-stu-id="d701b-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="d701b-110">[in] The name of the file containing the symbol store.</span><span class="sxs-lookup"><span data-stu-id="d701b-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="d701b-111">[in] The file stream, used as an alternative to the `filename` parameter.</span><span class="sxs-lookup"><span data-stu-id="d701b-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d701b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d701b-112">Return Value</span></span>  
 <span data-ttu-id="d701b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="d701b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d701b-114">要求</span><span class="sxs-lookup"><span data-stu-id="d701b-114">Requirements</span></span>  
 <span data-ttu-id="d701b-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d701b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d701b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d701b-116">See also</span></span>

- [<span data-ttu-id="d701b-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="d701b-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
