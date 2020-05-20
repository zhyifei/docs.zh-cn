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
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615470"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="ba8a2-102">ISymUnmanagedReader::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="ba8a2-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="ba8a2-103">用此读取器将与之关联的元数据导入程序接口以及模块的文件名初始化符号读取器。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba8a2-104">此方法只能调用一次，并且必须在任何其他读取器方法之前调用。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8a2-105">语法</span><span class="sxs-lookup"><span data-stu-id="ba8a2-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba8a2-106">参数</span><span class="sxs-lookup"><span data-stu-id="ba8a2-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="ba8a2-107">中此读取器将与之关联的元数据导入程序接口。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="ba8a2-108">中模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-108">[in] The file name of the module.</span></span> <span data-ttu-id="ba8a2-109">可以改为使用 `pIStream` 参数。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="ba8a2-110">中要搜索的路径。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-110">[in] The path to search.</span></span> <span data-ttu-id="ba8a2-111">该参数为可选参数。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="ba8a2-112">中文件流，用作 filename 参数的替代项。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba8a2-113">返回值</span><span class="sxs-lookup"><span data-stu-id="ba8a2-113">Return Value</span></span>  
 <span data-ttu-id="ba8a2-114">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba8a2-115">备注</span><span class="sxs-lookup"><span data-stu-id="ba8a2-115">Remarks</span></span>  
 <span data-ttu-id="ba8a2-116">只需指定 `filename` 或 `pIStream` 参数之一，而不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="ba8a2-117">`searchPath` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="ba8a2-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba8a2-118">要求</span><span class="sxs-lookup"><span data-stu-id="ba8a2-118">Requirements</span></span>  
 <span data-ttu-id="ba8a2-119">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="ba8a2-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8a2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba8a2-120">See also</span></span>

- [<span data-ttu-id="ba8a2-121">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="ba8a2-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
