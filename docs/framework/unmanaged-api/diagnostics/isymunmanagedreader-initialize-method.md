---
title: "ISymUnmanagedReader::Initialize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 433cd62f7801d386f3b34b7fc8e95bd1d0c5f765
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="6bc1c-102">ISymUnmanagedReader::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="6bc1c-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="6bc1c-103">初始化此读取器将与，以及该模块的文件名称相关联的元数据导入程序接口的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bc1c-104">此方法可以一次调用，必须在其他任何读取器方法之前调用。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc1c-105">语法</span><span class="sxs-lookup"><span data-stu-id="6bc1c-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bc1c-106">参数</span><span class="sxs-lookup"><span data-stu-id="6bc1c-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="6bc1c-107">[in]此读取器将与之关联的元数据导入程序接口。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="6bc1c-108">[in]模块的文件名称。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-108">[in] The file name of the module.</span></span> <span data-ttu-id="6bc1c-109">你可以使用`pIStream`参数相反。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="6bc1c-110">[in]要搜索的路径。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-110">[in] The path to search.</span></span> <span data-ttu-id="6bc1c-111">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="6bc1c-112">[in]文件流用作 filename 参数的替代方法。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bc1c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="6bc1c-113">Return Value</span></span>  
 <span data-ttu-id="6bc1c-114">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bc1c-115">备注</span><span class="sxs-lookup"><span data-stu-id="6bc1c-115">Remarks</span></span>  
 <span data-ttu-id="6bc1c-116">你需要只能指定其中一个`filename`或`pIStream`参数，不是两个。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="6bc1c-117">`searchPath` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="6bc1c-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bc1c-118">惠?</span><span class="sxs-lookup"><span data-stu-id="6bc1c-118">Requirements</span></span>  
 <span data-ttu-id="6bc1c-119">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6bc1c-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc1c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bc1c-120">See Also</span></span>  
 [<span data-ttu-id="6bc1c-121">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="6bc1c-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
