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
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="2c9e1-102">ISymUnmanagedBinder::GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="2c9e1-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="2c9e1-103">给定元数据接口和文件名后，将返回正确的[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口，该接口将读取与模块关联的调试符号。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="2c9e1-104">仅当程序数据库（PDB）文件位于可执行文件旁边时，此方法才会打开该文件。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="2c9e1-105">出于安全考虑，已进行了此更改。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-105">This change has been made for security purposes.</span></span> <span data-ttu-id="2c9e1-106">如果需要更广泛的 PDB 文件搜索，请使用[ISymUnmanagedBinder2：： GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c9e1-107">语法</span><span class="sxs-lookup"><span data-stu-id="2c9e1-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c9e1-108">参数</span><span class="sxs-lookup"><span data-stu-id="2c9e1-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="2c9e1-109">中指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="2c9e1-110">中指向文件名的指针。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="2c9e1-111">中指向搜索路径的指针。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2c9e1-112">弄设置为返回的[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c9e1-113">返回值</span><span class="sxs-lookup"><span data-stu-id="2c9e1-113">Return Value</span></span>  
 <span data-ttu-id="2c9e1-114">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c9e1-115">要求</span><span class="sxs-lookup"><span data-stu-id="2c9e1-115">Requirements</span></span>  
 <span data-ttu-id="2c9e1-116">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2c9e1-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9e1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c9e1-117">See also</span></span>

- [<span data-ttu-id="2c9e1-118">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="2c9e1-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="2c9e1-119">GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="2c9e1-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
