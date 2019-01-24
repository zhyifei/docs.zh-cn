---
title: ISymUnmanagedVariable 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50c38c5a9e1799a460c5be1f7234b36968dc3da2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706886"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="ae95c-102">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="ae95c-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="ae95c-103">表示一个变量，例如参数、 局部变量或字段。</span><span class="sxs-lookup"><span data-stu-id="ae95c-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae95c-104">方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-104">Methods</span></span>  
  
|<span data-ttu-id="ae95c-105">方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-105">Method</span></span>|<span data-ttu-id="ae95c-106">描述</span><span class="sxs-lookup"><span data-stu-id="ae95c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae95c-107">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="ae95c-108">获取此变量的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="ae95c-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="ae95c-109">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="ae95c-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="ae95c-110">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="ae95c-111">获取此变量的第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="ae95c-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="ae95c-112">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="ae95c-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="ae95c-113">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="ae95c-114">获取此变量的第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="ae95c-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="ae95c-115">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="ae95c-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="ae95c-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="ae95c-117">获取此变量的地址类型。</span><span class="sxs-lookup"><span data-stu-id="ae95c-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="ae95c-118">GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="ae95c-119">获取此变量的特性标志。</span><span class="sxs-lookup"><span data-stu-id="ae95c-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="ae95c-120">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="ae95c-121">获取此变量在其父级内的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="ae95c-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="ae95c-122">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="ae95c-123">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ae95c-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="ae95c-124">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="ae95c-125">获取此变量的签名。</span><span class="sxs-lookup"><span data-stu-id="ae95c-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="ae95c-126">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="ae95c-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="ae95c-127">获取此变量在其父级内的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="ae95c-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae95c-128">要求</span><span class="sxs-lookup"><span data-stu-id="ae95c-128">Requirements</span></span>  
 <span data-ttu-id="ae95c-129">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ae95c-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae95c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae95c-130">See also</span></span>
- [<span data-ttu-id="ae95c-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="ae95c-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
