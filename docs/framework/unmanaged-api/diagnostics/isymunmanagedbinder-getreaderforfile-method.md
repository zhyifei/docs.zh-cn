---
title: "ISymUnmanagedBinder::GetReaderForFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder.GetReaderForFile
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 856f7eb506f77181d41ebd10148f321197ebfda3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="32493-102">ISymUnmanagedBinder::GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="32493-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="32493-103">指定元数据接口和文件名称，则会返回正确 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 将读取与模块关联的调试符号的结构。</span><span class="sxs-lookup"><span data-stu-id="32493-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="32493-104">仅当它旁边的可执行文件时，此方法将打开程序数据库 (PDB) 文件。</span><span class="sxs-lookup"><span data-stu-id="32493-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="32493-105">出于安全目的做出此更改。</span><span class="sxs-lookup"><span data-stu-id="32493-105">This change has been made for security purposes.</span></span> <span data-ttu-id="32493-106">如果你需要的 PDB 文件更广泛的搜索，使用[isymunmanagedbinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="32493-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32493-107">语法</span><span class="sxs-lookup"><span data-stu-id="32493-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32493-108">参数</span><span class="sxs-lookup"><span data-stu-id="32493-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="32493-109">[in]指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="32493-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="32493-110">[in]指向的文件名称的指针。</span><span class="sxs-lookup"><span data-stu-id="32493-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="32493-111">[in]搜索路径指向的指针。</span><span class="sxs-lookup"><span data-stu-id="32493-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="32493-112">[out]一个指针，它设置为返回 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 接口。</span><span class="sxs-lookup"><span data-stu-id="32493-112">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32493-113">返回值</span><span class="sxs-lookup"><span data-stu-id="32493-113">Return Value</span></span>  
 <span data-ttu-id="32493-114">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="32493-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32493-115">要求</span><span class="sxs-lookup"><span data-stu-id="32493-115">Requirements</span></span>  
 <span data-ttu-id="32493-116">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="32493-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32493-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32493-117">See Also</span></span>  
 [<span data-ttu-id="32493-118">ISymUnmanagedBinder 接口</span><span class="sxs-lookup"><span data-stu-id="32493-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="32493-119">GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="32493-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
