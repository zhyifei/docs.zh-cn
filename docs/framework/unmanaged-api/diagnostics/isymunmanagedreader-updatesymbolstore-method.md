---
title: "ISymUnmanagedReader::UpdateSymbolStore 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.UpdateSymbolStore
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cfea77814069f6689f7492608548836fdafa591b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a><span data-ttu-id="c03f6-102">ISymUnmanagedReader::UpdateSymbolStore 方法</span><span class="sxs-lookup"><span data-stu-id="c03f6-102">ISymUnmanagedReader::UpdateSymbolStore Method</span></span>
<span data-ttu-id="c03f6-103">使用增量符号存储区更新现有的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="c03f6-103">Updates the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="c03f6-104">此方法在编辑并继续方案中用于更新要匹配的原始的可移植可执行 (PE) 文件的增量可以保持的符号存储区。</span><span class="sxs-lookup"><span data-stu-id="c03f6-104">This method is used in edit-and-continue scenarios to update the symbol store to match deltas to the original portable executable (PE) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c03f6-105">你需要只能指定其中一个`filename`或`pIStream`参数，不是两个。</span><span class="sxs-lookup"><span data-stu-id="c03f6-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="c03f6-106">如果`filename`指定，则将使用该文件中的符号更新符号存储区。</span><span class="sxs-lookup"><span data-stu-id="c03f6-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="c03f6-107">如果`pIStream`存储将更新中的数据的指定<xref:System.Runtime.InteropServices.ComTypes.IStream>。</span><span class="sxs-lookup"><span data-stu-id="c03f6-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c03f6-108">语法</span><span class="sxs-lookup"><span data-stu-id="c03f6-108">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c03f6-109">参数</span><span class="sxs-lookup"><span data-stu-id="c03f6-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="c03f6-110">[in]包含符号存储区的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c03f6-110">[in] The name of the file that contains the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="c03f6-111">[in]文件流，用作替代`filename`参数。</span><span class="sxs-lookup"><span data-stu-id="c03f6-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c03f6-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c03f6-112">Return Value</span></span>  
 <span data-ttu-id="c03f6-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c03f6-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c03f6-114">要求</span><span class="sxs-lookup"><span data-stu-id="c03f6-114">Requirements</span></span>  
 <span data-ttu-id="c03f6-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c03f6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c03f6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c03f6-116">See Also</span></span>  
 [<span data-ttu-id="c03f6-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="c03f6-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
