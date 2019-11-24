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
ms.openlocfilehash: 94cda16466ea5a3d35a478a2ae80281e9414f719
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449356"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="3590e-102">ISymUnmanagedBinder::GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="3590e-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="3590e-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span><span class="sxs-lookup"><span data-stu-id="3590e-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="3590e-104">This method will open the program database (PDB) file only if it is next to the executable file.</span><span class="sxs-lookup"><span data-stu-id="3590e-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="3590e-105">This change has been made for security purposes.</span><span class="sxs-lookup"><span data-stu-id="3590e-105">This change has been made for security purposes.</span></span> <span data-ttu-id="3590e-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="3590e-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3590e-107">语法</span><span class="sxs-lookup"><span data-stu-id="3590e-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3590e-108">参数</span><span class="sxs-lookup"><span data-stu-id="3590e-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="3590e-109">[in] A pointer to the metadata import interface.</span><span class="sxs-lookup"><span data-stu-id="3590e-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="3590e-110">[in] A pointer to the file name.</span><span class="sxs-lookup"><span data-stu-id="3590e-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="3590e-111">[in] A pointer to the search path.</span><span class="sxs-lookup"><span data-stu-id="3590e-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3590e-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="3590e-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3590e-113">返回值</span><span class="sxs-lookup"><span data-stu-id="3590e-113">Return Value</span></span>  
 <span data-ttu-id="3590e-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="3590e-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3590e-115">要求</span><span class="sxs-lookup"><span data-stu-id="3590e-115">Requirements</span></span>  
 <span data-ttu-id="3590e-116">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3590e-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3590e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3590e-117">See also</span></span>

- [<span data-ttu-id="3590e-118">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="3590e-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="3590e-119">GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="3590e-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
