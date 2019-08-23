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
ms.openlocfilehash: f2dceeb2f0b3aa9f3147157e77087dffbf2d5f85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939011"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="0c19e-102">ISymUnmanagedReader::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="0c19e-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="0c19e-103">用此读取器将与之关联的元数据导入程序接口以及模块的文件名初始化符号读取器。</span><span class="sxs-lookup"><span data-stu-id="0c19e-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c19e-104">此方法只能调用一次, 并且必须在任何其他读取器方法之前调用。</span><span class="sxs-lookup"><span data-stu-id="0c19e-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c19e-105">语法</span><span class="sxs-lookup"><span data-stu-id="0c19e-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c19e-106">参数</span><span class="sxs-lookup"><span data-stu-id="0c19e-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="0c19e-107">中此读取器将与之关联的元数据导入程序接口。</span><span class="sxs-lookup"><span data-stu-id="0c19e-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="0c19e-108">中模块的文件名。</span><span class="sxs-lookup"><span data-stu-id="0c19e-108">[in] The file name of the module.</span></span> <span data-ttu-id="0c19e-109">可以改为`pIStream`使用参数。</span><span class="sxs-lookup"><span data-stu-id="0c19e-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="0c19e-110">中要搜索的路径。</span><span class="sxs-lookup"><span data-stu-id="0c19e-110">[in] The path to search.</span></span> <span data-ttu-id="0c19e-111">此参数可选。</span><span class="sxs-lookup"><span data-stu-id="0c19e-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="0c19e-112">中文件流, 用作 filename 参数的替代项。</span><span class="sxs-lookup"><span data-stu-id="0c19e-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c19e-113">返回值</span><span class="sxs-lookup"><span data-stu-id="0c19e-113">Return Value</span></span>  
 <span data-ttu-id="0c19e-114">如果该方法成功, 则返回 S_OK;否则, E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="0c19e-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c19e-115">备注</span><span class="sxs-lookup"><span data-stu-id="0c19e-115">Remarks</span></span>  
 <span data-ttu-id="0c19e-116">只需指定`filename` `pIStream`或参数之一, 而不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="0c19e-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="0c19e-117">`searchPath` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="0c19e-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c19e-118">要求</span><span class="sxs-lookup"><span data-stu-id="0c19e-118">Requirements</span></span>  
 <span data-ttu-id="0c19e-119">**标头：** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="0c19e-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c19e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c19e-120">See also</span></span>

- [<span data-ttu-id="0c19e-121">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="0c19e-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
