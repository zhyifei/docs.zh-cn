---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 5afd48b36355835647ab8d06691f2bd2058b00cb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426735"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="6e476-102">ISymUnmanagedReader::GetMethodFromDocumentPosition 方法</span><span class="sxs-lookup"><span data-stu-id="6e476-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="6e476-103">返回包含文档中给定位置处的断点的方法。</span><span class="sxs-lookup"><span data-stu-id="6e476-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e476-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e476-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e476-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e476-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="6e476-106">中指定的文档。</span><span class="sxs-lookup"><span data-stu-id="6e476-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="6e476-107">中指定文档的行。</span><span class="sxs-lookup"><span data-stu-id="6e476-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="6e476-108">中指定文档的列。</span><span class="sxs-lookup"><span data-stu-id="6e476-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="6e476-109">弄指向表示包含断点的方法的[ISymUnmanagedMethod 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6e476-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e476-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6e476-110">Return Value</span></span>  
 <span data-ttu-id="6e476-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="6e476-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e476-112">要求</span><span class="sxs-lookup"><span data-stu-id="6e476-112">Requirements</span></span>  
 <span data-ttu-id="6e476-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="6e476-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e476-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e476-114">See also</span></span>

- [<span data-ttu-id="6e476-115">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="6e476-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
