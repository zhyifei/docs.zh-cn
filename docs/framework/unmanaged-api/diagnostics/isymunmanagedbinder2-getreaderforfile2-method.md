---
title: ISymUnmanagedBinder2::GetReaderForFile2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fed289b2776e8ac4a12969060cd16c6163ebed2f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091962"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="279b1-102">ISymUnmanagedBinder2::GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="279b1-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="279b1-103">给定元数据接口和文件名称，返回的正确[ISymUnmanagedReader](isymunmanagedreader-interface.md)将读取与模块关联的调试符号的接口。</span><span class="sxs-lookup"><span data-stu-id="279b1-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="279b1-104">此方法提供了更广泛的搜索的程序数据库 (PDB) 文件比[isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="279b1-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="279b1-105">语法</span><span class="sxs-lookup"><span data-stu-id="279b1-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="279b1-106">参数</span><span class="sxs-lookup"><span data-stu-id="279b1-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="279b1-107">[in]指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="279b1-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="279b1-108">[in]一个指向的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="279b1-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="279b1-109">[in]搜索路径指向的指针。</span><span class="sxs-lookup"><span data-stu-id="279b1-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="279b1-110">[in]值为[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)枚举，用于指定要执行的符号读取器的搜索时使用的策略。</span><span class="sxs-lookup"><span data-stu-id="279b1-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="279b1-111">[out]一个指针，它设置为返回[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="279b1-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="279b1-112">返回值</span><span class="sxs-lookup"><span data-stu-id="279b1-112">Return Value</span></span>  
 <span data-ttu-id="279b1-113">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="279b1-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="279b1-114">要求</span><span class="sxs-lookup"><span data-stu-id="279b1-114">Requirements</span></span>  
 <span data-ttu-id="279b1-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="279b1-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="279b1-116">备注</span><span class="sxs-lookup"><span data-stu-id="279b1-116">Remarks</span></span>  
 <span data-ttu-id="279b1-117">此版本的方法可以搜索该模块的旁边以外的区域中的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="279b1-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="279b1-118">搜索策略可以控制通过组合[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="279b1-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="279b1-119">例如，`AllowReferencePathAccess | AllowSymbolServerAccess`查找 PDB 旁边的可执行文件，在符号服务器上，但不查询注册表或可执行文件中使用的路径。</span><span class="sxs-lookup"><span data-stu-id="279b1-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="279b1-120">如果`searchPath`提供参数，将始终搜索这些目录。</span><span class="sxs-lookup"><span data-stu-id="279b1-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279b1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="279b1-121">See also</span></span>

- [<span data-ttu-id="279b1-122">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="279b1-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="279b1-123">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="279b1-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
