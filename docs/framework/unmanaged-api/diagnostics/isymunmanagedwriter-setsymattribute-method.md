---
title: ISymUnmanagedWriter::SetSymAttribute 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4450c262b75a73114cb7de7de98567f053bbf564
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894467"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="6e8c8-102">ISymUnmanagedWriter::SetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="6e8c8-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="6e8c8-103">基于名称定义自定义属性。</span><span class="sxs-lookup"><span data-stu-id="6e8c8-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="6e8c8-104">这些特性保存在符号存储区中，与元数据自定义特性不同。</span><span class="sxs-lookup"><span data-stu-id="6e8c8-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e8c8-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e8c8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e8c8-106">参数</span><span class="sxs-lookup"><span data-stu-id="6e8c8-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="6e8c8-107">中正在为其定义特性的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="6e8c8-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="6e8c8-108">中指向`WCHAR`包含特性名称的的指针。</span><span class="sxs-lookup"><span data-stu-id="6e8c8-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="6e8c8-109">中`ULONG32`指示`data`数组大小的。</span><span class="sxs-lookup"><span data-stu-id="6e8c8-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="6e8c8-110">中特性值。</span><span class="sxs-lookup"><span data-stu-id="6e8c8-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e8c8-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6e8c8-111">Return Value</span></span>  
 <span data-ttu-id="6e8c8-112">如果该方法成功，则返回 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="6e8c8-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e8c8-113">要求</span><span class="sxs-lookup"><span data-stu-id="6e8c8-113">Requirements</span></span>  
 <span data-ttu-id="6e8c8-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="6e8c8-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e8c8-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e8c8-115">See also</span></span>

- [<span data-ttu-id="6e8c8-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6e8c8-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
