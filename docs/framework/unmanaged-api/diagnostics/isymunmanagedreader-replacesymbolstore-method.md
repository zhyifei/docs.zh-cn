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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8721f7c30061fbfd4a761bed090b761762c3c13c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939023"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="4c69b-102">ISymUnmanagedReader::ReplaceSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="4c69b-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="4c69b-103">用增量符号存储区替换现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="4c69b-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="4c69b-104">此方法类似于[UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)方法, 不同之处在于给定增量充当完全替换而不是更新。</span><span class="sxs-lookup"><span data-stu-id="4c69b-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c69b-105">只需指定`filename`或`pIStream`参数之一, 而不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="4c69b-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="4c69b-106">如果`filename`指定了, 则将用该文件中的符号更新符号存储区。</span><span class="sxs-lookup"><span data-stu-id="4c69b-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="4c69b-107">如果`pIStream`指定了, 则将用<xref:System.Runtime.InteropServices.ComTypes.IStream>中的数据更新存储区。</span><span class="sxs-lookup"><span data-stu-id="4c69b-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c69b-108">语法</span><span class="sxs-lookup"><span data-stu-id="4c69b-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c69b-109">参数</span><span class="sxs-lookup"><span data-stu-id="4c69b-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="4c69b-110">中包含符号存储区的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4c69b-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="4c69b-111">中文件流, 用作`filename`参数的替代项。</span><span class="sxs-lookup"><span data-stu-id="4c69b-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c69b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="4c69b-112">Return Value</span></span>  
 <span data-ttu-id="4c69b-113">如果该方法成功, 则返回 S_OK;否则, E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="4c69b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c69b-114">要求</span><span class="sxs-lookup"><span data-stu-id="4c69b-114">Requirements</span></span>  
 <span data-ttu-id="4c69b-115">**标头：** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4c69b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c69b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c69b-116">See also</span></span>

- [<span data-ttu-id="4c69b-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="4c69b-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
