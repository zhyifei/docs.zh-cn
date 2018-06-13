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
ms.openlocfilehash: 3db4fc691637c049e0374416cb92a2056555ad11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428695"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="dd025-102">ISymUnmanagedVariable 接口</span><span class="sxs-lookup"><span data-stu-id="dd025-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="dd025-103">表示一个变量，例如参数、 本地变量或字段。</span><span class="sxs-lookup"><span data-stu-id="dd025-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd025-104">方法</span><span class="sxs-lookup"><span data-stu-id="dd025-104">Methods</span></span>  
  
|<span data-ttu-id="dd025-105">方法</span><span class="sxs-lookup"><span data-stu-id="dd025-105">Method</span></span>|<span data-ttu-id="dd025-106">描述</span><span class="sxs-lookup"><span data-stu-id="dd025-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd025-107">GetAddressField1 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="dd025-108">获取此变量的第一个地址字段。</span><span class="sxs-lookup"><span data-stu-id="dd025-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="dd025-109">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="dd025-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="dd025-110">GetAddressField2 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="dd025-111">获取此变量的第二个地址字段。</span><span class="sxs-lookup"><span data-stu-id="dd025-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="dd025-112">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="dd025-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="dd025-113">GetAddressField3 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="dd025-114">获取此变量的第三个地址字段。</span><span class="sxs-lookup"><span data-stu-id="dd025-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="dd025-115">其含义取决于类型的地址。</span><span class="sxs-lookup"><span data-stu-id="dd025-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="dd025-116">GetAddressKind 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="dd025-117">获取此变量的地址的种类。</span><span class="sxs-lookup"><span data-stu-id="dd025-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="dd025-118">GetAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="dd025-119">获取此变量的属性的标志。</span><span class="sxs-lookup"><span data-stu-id="dd025-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="dd025-120">GetEndOffset 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="dd025-121">获取其父项中此变量的结束偏移量。</span><span class="sxs-lookup"><span data-stu-id="dd025-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="dd025-122">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="dd025-123">获取此变量的名称。</span><span class="sxs-lookup"><span data-stu-id="dd025-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="dd025-124">GetSignature 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="dd025-125">获取此变量的签名。</span><span class="sxs-lookup"><span data-stu-id="dd025-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="dd025-126">GetStartOffset 方法</span><span class="sxs-lookup"><span data-stu-id="dd025-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="dd025-127">获取此变量在其父级内的起始偏移量。</span><span class="sxs-lookup"><span data-stu-id="dd025-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dd025-128">要求</span><span class="sxs-lookup"><span data-stu-id="dd025-128">Requirements</span></span>  
 <span data-ttu-id="dd025-129">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dd025-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd025-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd025-130">See Also</span></span>  
 [<span data-ttu-id="dd025-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="dd025-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
