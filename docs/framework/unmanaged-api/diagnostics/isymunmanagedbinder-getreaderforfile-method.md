---
title: ISymUnmanagedBinder::GetReaderForFile 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0414cadca910f3290f96a841e3f807f0de469606
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145959"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="e52b2-102">ISymUnmanagedBinder::GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="e52b2-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="e52b2-103">给定元数据接口和文件名称，返回的正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)将读取与模块关联的调试符号的接口。</span><span class="sxs-lookup"><span data-stu-id="e52b2-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="e52b2-104">仅当可执行文件旁边，此方法将打开程序数据库 (PDB) 文件。</span><span class="sxs-lookup"><span data-stu-id="e52b2-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="e52b2-105">以安全为目的做出此更改。</span><span class="sxs-lookup"><span data-stu-id="e52b2-105">This change has been made for security purposes.</span></span> <span data-ttu-id="e52b2-106">如果你需要的 PDB 文件更广泛的搜索，使用[ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e52b2-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e52b2-107">语法</span><span class="sxs-lookup"><span data-stu-id="e52b2-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e52b2-108">参数</span><span class="sxs-lookup"><span data-stu-id="e52b2-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="e52b2-109">[in]指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="e52b2-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="e52b2-110">[in]一个指向的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e52b2-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="e52b2-111">[in]搜索路径指向的指针。</span><span class="sxs-lookup"><span data-stu-id="e52b2-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e52b2-112">[out]一个指针，它设置为返回[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e52b2-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e52b2-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e52b2-113">Return Value</span></span>  
 <span data-ttu-id="e52b2-114">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="e52b2-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e52b2-115">要求</span><span class="sxs-lookup"><span data-stu-id="e52b2-115">Requirements</span></span>  
 <span data-ttu-id="e52b2-116">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e52b2-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e52b2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e52b2-117">See also</span></span>

- [<span data-ttu-id="e52b2-118">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="e52b2-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="e52b2-119">GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="e52b2-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
