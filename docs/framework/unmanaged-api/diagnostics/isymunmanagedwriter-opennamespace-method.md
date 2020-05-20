---
title: ISymUnmanagedWriter::OpenNamespace 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: ab248c6a624fbed1a6783383566be093c449ff97
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609880"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="3a801-102">ISymUnmanagedWriter::OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="3a801-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="3a801-103">打开一个新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3a801-103">Opens a new namespace.</span></span> <span data-ttu-id="3a801-104">在定义占用命名空间的方法或变量之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="3a801-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="3a801-105">命名空间可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="3a801-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a801-106">语法</span><span class="sxs-lookup"><span data-stu-id="3a801-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a801-107">参数</span><span class="sxs-lookup"><span data-stu-id="3a801-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3a801-108">中指向新命名空间的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="3a801-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a801-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3a801-109">Return Value</span></span>  
 <span data-ttu-id="3a801-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3a801-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a801-111">要求</span><span class="sxs-lookup"><span data-stu-id="3a801-111">Requirements</span></span>  
 <span data-ttu-id="3a801-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3a801-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a801-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a801-113">See also</span></span>

- [<span data-ttu-id="3a801-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="3a801-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="3a801-115">CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="3a801-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)
