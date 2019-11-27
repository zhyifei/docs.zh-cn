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
ms.openlocfilehash: 756ba2e71ca2e3e817a0a8b89165bb807368c1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449330"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="7cabf-102">ISymUnmanagedBinder2::GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="7cabf-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="7cabf-103">给定元数据接口和文件名后，将返回正确的[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口，该接口将读取与模块关联的调试符号。</span><span class="sxs-lookup"><span data-stu-id="7cabf-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="7cabf-104">与[ISymUnmanagedBinder：： GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)方法相比，此方法提供更广泛的程序数据库（PDB）文件搜索。</span><span class="sxs-lookup"><span data-stu-id="7cabf-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cabf-105">语法</span><span class="sxs-lookup"><span data-stu-id="7cabf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cabf-106">参数</span><span class="sxs-lookup"><span data-stu-id="7cabf-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="7cabf-107">中指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="7cabf-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="7cabf-108">中指向文件名的指针。</span><span class="sxs-lookup"><span data-stu-id="7cabf-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="7cabf-109">中指向搜索路径的指针。</span><span class="sxs-lookup"><span data-stu-id="7cabf-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="7cabf-110">中[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)枚举的一个值，该值指定在搜索符号读取器时要使用的策略。</span><span class="sxs-lookup"><span data-stu-id="7cabf-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="7cabf-111">弄设置为返回的[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="7cabf-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cabf-112">返回值</span><span class="sxs-lookup"><span data-stu-id="7cabf-112">Return Value</span></span>  
 <span data-ttu-id="7cabf-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="7cabf-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cabf-114">要求</span><span class="sxs-lookup"><span data-stu-id="7cabf-114">Requirements</span></span>  
 <span data-ttu-id="7cabf-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="7cabf-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cabf-116">备注</span><span class="sxs-lookup"><span data-stu-id="7cabf-116">Remarks</span></span>  
 <span data-ttu-id="7cabf-117">此版本的方法可在模块旁的其他区域中搜索 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="7cabf-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="7cabf-118">可以通过组合[CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)来控制搜索策略。</span><span class="sxs-lookup"><span data-stu-id="7cabf-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="7cabf-119">例如，`AllowReferencePathAccess | AllowSymbolServerAccess` 将在可执行文件和符号服务器上查找 PDB，但不查询注册表或使用可执行文件中的路径。</span><span class="sxs-lookup"><span data-stu-id="7cabf-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="7cabf-120">如果提供了 `searchPath` 参数，则将始终搜索这些目录。</span><span class="sxs-lookup"><span data-stu-id="7cabf-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cabf-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cabf-121">See also</span></span>

- [<span data-ttu-id="7cabf-122">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="7cabf-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="7cabf-123">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="7cabf-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
