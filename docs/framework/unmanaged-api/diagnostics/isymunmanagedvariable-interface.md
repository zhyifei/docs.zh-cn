---
title: "ISymUnmanagedVariable 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable
helpviewer_keywords: ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c32d5b66c575a21b4d390cff560b71f93aa31927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="52910-102">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="52910-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="52910-103">表示一个变量，例如参数、 本地变量或字段。</span><span class="sxs-lookup"><span data-stu-id="52910-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52910-104">方法</span><span class="sxs-lookup"><span data-stu-id="52910-104">Methods</span></span>  
  
|<span data-ttu-id="52910-105">方法</span><span class="sxs-lookup"><span data-stu-id="52910-105">Method</span></span>|<span data-ttu-id="52910-106">描述</span><span class="sxs-lookup"><span data-stu-id="52910-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52910-107">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="52910-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="52910-108">获取此变量的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="52910-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="52910-109">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="52910-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="52910-110">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="52910-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="52910-111">获取此变量的第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="52910-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="52910-112">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="52910-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="52910-113">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="52910-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="52910-114">获取此变量的第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="52910-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="52910-115">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="52910-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="52910-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="52910-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="52910-117">获取此变量的地址的种类。</span><span class="sxs-lookup"><span data-stu-id="52910-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="52910-118">GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="52910-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="52910-119">获取此变量的属性的标志。</span><span class="sxs-lookup"><span data-stu-id="52910-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="52910-120">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="52910-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="52910-121">获取其父项中此变量的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="52910-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="52910-122">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="52910-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="52910-123">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="52910-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="52910-124">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="52910-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="52910-125">获取此变量的签名。</span><span class="sxs-lookup"><span data-stu-id="52910-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="52910-126">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="52910-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="52910-127">获取此变量在其父级内的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="52910-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52910-128">要求</span><span class="sxs-lookup"><span data-stu-id="52910-128">Requirements</span></span>  
 <span data-ttu-id="52910-129">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52910-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52910-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52910-130">See Also</span></span>  
 [<span data-ttu-id="52910-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="52910-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
