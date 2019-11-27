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
ms.openlocfilehash: 8a4d205586921b377147eeab80754e1a0d9e52b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427840"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="cb79b-102">ISymUnmanagedWriter::SetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="cb79b-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="cb79b-103">基于名称定义自定义属性。</span><span class="sxs-lookup"><span data-stu-id="cb79b-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="cb79b-104">这些特性保存在符号存储区中，与元数据自定义特性不同。</span><span class="sxs-lookup"><span data-stu-id="cb79b-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb79b-105">语法</span><span class="sxs-lookup"><span data-stu-id="cb79b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb79b-106">参数</span><span class="sxs-lookup"><span data-stu-id="cb79b-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="cb79b-107">中正在为其定义特性的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="cb79b-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="cb79b-108">中指向包含特性名称的 `WCHAR` 的指针。</span><span class="sxs-lookup"><span data-stu-id="cb79b-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="cb79b-109">中一个 `ULONG32`，指示 `data` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="cb79b-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="cb79b-110">中特性值。</span><span class="sxs-lookup"><span data-stu-id="cb79b-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb79b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="cb79b-111">Return Value</span></span>  
 <span data-ttu-id="cb79b-112">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="cb79b-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb79b-113">要求</span><span class="sxs-lookup"><span data-stu-id="cb79b-113">Requirements</span></span>  
 <span data-ttu-id="cb79b-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="cb79b-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb79b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb79b-115">See also</span></span>

- [<span data-ttu-id="cb79b-116">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="cb79b-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
