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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f62c954bf9d73ab564eba388e742794a330362d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080496"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="9f019-102">ISymUnmanagedReader::UpdateSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="9f019-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="9f019-103">使用增量符号存储区更新现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="9f019-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="9f019-104">此方法在编辑并继续方案中用于更新符号存储区以匹配的原始的可移植可执行 (PE) 文件的增量。</span><span class="sxs-lookup"><span data-stu-id="9f019-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f019-105">你需要仅指定一个`filename`或`pIStream`参数不可同时使用两者。</span><span class="sxs-lookup"><span data-stu-id="9f019-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="9f019-106">如果`filename`指定，则将使用该文件中的符号更新符号存储区。</span><span class="sxs-lookup"><span data-stu-id="9f019-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="9f019-107">如果`pIStream`中的数据将更新存储的指定<xref:System.Runtime.InteropServices.ComTypes.IStream>。</span><span class="sxs-lookup"><span data-stu-id="9f019-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f019-108">语法</span><span class="sxs-lookup"><span data-stu-id="9f019-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f019-109">参数</span><span class="sxs-lookup"><span data-stu-id="9f019-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="9f019-110">[in]包含符号存储区的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9f019-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="9f019-111">[in]作为一种替代方法使用的文件流`filename`参数。</span><span class="sxs-lookup"><span data-stu-id="9f019-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f019-112">返回值</span><span class="sxs-lookup"><span data-stu-id="9f019-112">Return Value</span></span>  
 <span data-ttu-id="9f019-113">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="9f019-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f019-114">要求</span><span class="sxs-lookup"><span data-stu-id="9f019-114">Requirements</span></span>  
 <span data-ttu-id="9f019-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9f019-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f019-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f019-116">See also</span></span>

- [<span data-ttu-id="9f019-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="9f019-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
