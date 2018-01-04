---
title: "ISymUnmanagedBinder2::GetReaderForFile2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2.GetReaderForFile2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 270a154c40b85ad4774bececf12685393f4d6c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="bb251-102">ISymUnmanagedBinder2::GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="bb251-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="bb251-103">指定元数据接口和文件名称，则会返回正确 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 将读取与模块关联的调试符号的接口。</span><span class="sxs-lookup"><span data-stu-id="bb251-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="bb251-104">此方法提供的程序数据库 (PDB) 文件而非更广泛的搜索[isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bb251-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb251-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb251-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb251-106">参数</span><span class="sxs-lookup"><span data-stu-id="bb251-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="bb251-107">[in]指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="bb251-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="bb251-108">[in]指向的文件名称的指针。</span><span class="sxs-lookup"><span data-stu-id="bb251-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="bb251-109">[in]搜索路径指向的指针。</span><span class="sxs-lookup"><span data-stu-id="bb251-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="bb251-110">[in]值为[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)枚举，它指定要执行搜索的符号读取器时使用的策略。</span><span class="sxs-lookup"><span data-stu-id="bb251-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="bb251-111">[out]一个指针，它设置为返回 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 接口。</span><span class="sxs-lookup"><span data-stu-id="bb251-111">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb251-112">返回值</span><span class="sxs-lookup"><span data-stu-id="bb251-112">Return Value</span></span>  
 <span data-ttu-id="bb251-113">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="bb251-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb251-114">惠?</span><span class="sxs-lookup"><span data-stu-id="bb251-114">Requirements</span></span>  
 <span data-ttu-id="bb251-115">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bb251-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb251-116">备注</span><span class="sxs-lookup"><span data-stu-id="bb251-116">Remarks</span></span>  
 <span data-ttu-id="bb251-117">此版本的方法可以搜索区域以外的旁边，该模块中的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="bb251-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="bb251-118">搜索策略可以控制通过组合[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="bb251-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="bb251-119">例如，`AllowReferencePathAccess | AllowSymbolServerAccess`寻找 PDB 的可执行文件旁边和符号服务器，但不会查询注册表或可执行文件中使用的路径。</span><span class="sxs-lookup"><span data-stu-id="bb251-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="bb251-120">如果`searchPath`提供参数，这些目录将始终搜索。</span><span class="sxs-lookup"><span data-stu-id="bb251-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb251-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb251-121">See Also</span></span>  
 [<span data-ttu-id="bb251-122">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="bb251-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="bb251-123">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="bb251-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
