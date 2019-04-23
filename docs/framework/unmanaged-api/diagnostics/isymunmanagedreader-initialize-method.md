---
title: ISymUnmanagedReader::Initialize 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 661c27b9c21f77104b8a86163d3c92d44f8a85df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181774"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="3f3eb-102">ISymUnmanagedReader::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="3f3eb-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="3f3eb-103">初始化此读取器将与相关联，以及该模块的文件名称的元数据导入程序接口的符号读取器。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f3eb-104">此方法可以将只调用一次，并必须读取器的任何其他方法之前调用。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f3eb-105">语法</span><span class="sxs-lookup"><span data-stu-id="3f3eb-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f3eb-106">参数</span><span class="sxs-lookup"><span data-stu-id="3f3eb-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="3f3eb-107">[in]此读取器将与之关联的元数据导入程序接口。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="3f3eb-108">[in]模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-108">[in] The file name of the module.</span></span> <span data-ttu-id="3f3eb-109">可以使用`pIStream`参数相反。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="3f3eb-110">[in]要搜索的路径。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-110">[in] The path to search.</span></span> <span data-ttu-id="3f3eb-111">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="3f3eb-112">[in]文件流用作 filename 参数的替代方法。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f3eb-113">返回值</span><span class="sxs-lookup"><span data-stu-id="3f3eb-113">Return Value</span></span>  
 <span data-ttu-id="3f3eb-114">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f3eb-115">备注</span><span class="sxs-lookup"><span data-stu-id="3f3eb-115">Remarks</span></span>  
 <span data-ttu-id="3f3eb-116">你需要仅指定一个`filename`或`pIStream`参数不可同时使用两者。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="3f3eb-117">`searchPath` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="3f3eb-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f3eb-118">要求</span><span class="sxs-lookup"><span data-stu-id="3f3eb-118">Requirements</span></span>  
 <span data-ttu-id="3f3eb-119">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3f3eb-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3eb-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f3eb-120">See also</span></span>

- [<span data-ttu-id="3f3eb-121">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="3f3eb-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
