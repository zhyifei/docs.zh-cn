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
ms.openlocfilehash: 97b9fa537fdd9147d6d9eda036013add5393e33c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441703"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="428a6-102">ISymUnmanagedBinder2::GetReaderForFile2 方法</span><span class="sxs-lookup"><span data-stu-id="428a6-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="428a6-103">给定元数据接口和文件名后，将返回正确的[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口，该接口将读取与模块关联的调试符号。</span><span class="sxs-lookup"><span data-stu-id="428a6-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="428a6-104">与[ISymUnmanagedBinder：： GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md)方法相比，此方法提供更广泛的程序数据库（PDB）文件搜索。</span><span class="sxs-lookup"><span data-stu-id="428a6-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="428a6-105">语法</span><span class="sxs-lookup"><span data-stu-id="428a6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="428a6-106">参数</span><span class="sxs-lookup"><span data-stu-id="428a6-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="428a6-107">中指向元数据导入接口的指针。</span><span class="sxs-lookup"><span data-stu-id="428a6-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="428a6-108">中指向文件名的指针。</span><span class="sxs-lookup"><span data-stu-id="428a6-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="428a6-109">中指向搜索路径的指针。</span><span class="sxs-lookup"><span data-stu-id="428a6-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="428a6-110">中[CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md)枚举的一个值，该值指定在搜索符号读取器时要使用的策略。</span><span class="sxs-lookup"><span data-stu-id="428a6-110">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="428a6-111">弄设置为返回的[ISymUnmanagedReader](isymunmanagedreader-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="428a6-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="428a6-112">返回值</span><span class="sxs-lookup"><span data-stu-id="428a6-112">Return Value</span></span>  
 <span data-ttu-id="428a6-113">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="428a6-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="428a6-114">要求</span><span class="sxs-lookup"><span data-stu-id="428a6-114">Requirements</span></span>  
 <span data-ttu-id="428a6-115">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="428a6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="428a6-116">备注</span><span class="sxs-lookup"><span data-stu-id="428a6-116">Remarks</span></span>  
 <span data-ttu-id="428a6-117">此版本的方法可在模块旁的其他区域中搜索 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="428a6-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="428a6-118">可以通过组合[CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md)来控制搜索策略。</span><span class="sxs-lookup"><span data-stu-id="428a6-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="428a6-119">例如，将在 `AllowReferencePathAccess | AllowSymbolServerAccess` 可执行文件和符号服务器上查找 PDB，但不查询注册表或使用可执行文件中的路径。</span><span class="sxs-lookup"><span data-stu-id="428a6-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="428a6-120">如果 `searchPath` 提供了参数，将始终搜索这些目录。</span><span class="sxs-lookup"><span data-stu-id="428a6-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="428a6-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="428a6-121">See also</span></span>

- [<span data-ttu-id="428a6-122">ISymUnmanagedBinder2 接口</span><span class="sxs-lookup"><span data-stu-id="428a6-122">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="428a6-123">GetReaderForFile 方法</span><span class="sxs-lookup"><span data-stu-id="428a6-123">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)
