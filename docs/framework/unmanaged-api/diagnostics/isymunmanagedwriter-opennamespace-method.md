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
ms.openlocfilehash: acbd49de7362d9c05a609a2d870af100637e10ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427902"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="05d29-102">ISymUnmanagedWriter::OpenNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="05d29-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="05d29-103">打开一个新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="05d29-103">Opens a new namespace.</span></span> <span data-ttu-id="05d29-104">在定义占用命名空间的方法或变量之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="05d29-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="05d29-105">命名空间可以嵌套。</span><span class="sxs-lookup"><span data-stu-id="05d29-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d29-106">语法</span><span class="sxs-lookup"><span data-stu-id="05d29-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05d29-107">参数</span><span class="sxs-lookup"><span data-stu-id="05d29-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="05d29-108">中指向新命名空间的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="05d29-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05d29-109">返回值</span><span class="sxs-lookup"><span data-stu-id="05d29-109">Return Value</span></span>  
 <span data-ttu-id="05d29-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="05d29-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d29-111">要求</span><span class="sxs-lookup"><span data-stu-id="05d29-111">Requirements</span></span>  
 <span data-ttu-id="05d29-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="05d29-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d29-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05d29-113">See also</span></span>

- [<span data-ttu-id="05d29-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="05d29-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="05d29-115">CloseNamespace 方法</span><span class="sxs-lookup"><span data-stu-id="05d29-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
