---
title: ISymUnmanagedDocument 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33213aced635549dd439cf679d89367a71baa7c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939771"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="f5c14-102">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="f5c14-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="f5c14-103">表示由符号存储引用的文档。</span><span class="sxs-lookup"><span data-stu-id="f5c14-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="f5c14-104">文档由统一资源定位器 (URL) 和 GUID 的文档类型定义。</span><span class="sxs-lookup"><span data-stu-id="f5c14-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="f5c14-105">可以找到而不考虑如何存储使用的 URL 的文档和文档类型的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f5c14-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="f5c14-106">可以在符号存储区中存储的文档源并检索通过此接口。</span><span class="sxs-lookup"><span data-stu-id="f5c14-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5c14-107">方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-107">Methods</span></span>  
  
|<span data-ttu-id="f5c14-108">方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-108">Method</span></span>|<span data-ttu-id="f5c14-109">描述</span><span class="sxs-lookup"><span data-stu-id="f5c14-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5c14-110">FindClosestLine 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="f5c14-111">返回一个序列点，最近的一行，可能也可能不是序列点本文档中提供一条线。</span><span class="sxs-lookup"><span data-stu-id="f5c14-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="f5c14-112">GetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="f5c14-113">获取校验和。</span><span class="sxs-lookup"><span data-stu-id="f5c14-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="f5c14-114">GetCheckSumAlgorithmId 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="f5c14-115">获取校验和算法标识符，或如果没有校验和，则返回全部为零的 GUID。</span><span class="sxs-lookup"><span data-stu-id="f5c14-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="f5c14-116">GetDocumentType 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="f5c14-117">获取此文档的文档类型。</span><span class="sxs-lookup"><span data-stu-id="f5c14-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="f5c14-118">GetLanguage 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="f5c14-119">获取此文档的语言标识符。</span><span class="sxs-lookup"><span data-stu-id="f5c14-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="f5c14-120">GetLanguageVendor 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="f5c14-121">获取此文档的语言供应商。</span><span class="sxs-lookup"><span data-stu-id="f5c14-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="f5c14-122">GetSourceLength 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="f5c14-123">获取嵌入源的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="f5c14-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="f5c14-124">GetSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="f5c14-125">返回到给定缓冲区中指定的嵌入的源范围。</span><span class="sxs-lookup"><span data-stu-id="f5c14-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="f5c14-126">GetURL 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="f5c14-127">返回此文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="f5c14-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="f5c14-128">HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="f5c14-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="f5c14-129">返回`true`如果该文档具有源嵌入在调试的符号; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="f5c14-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5c14-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5c14-130">See also</span></span>

- [<span data-ttu-id="f5c14-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="f5c14-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
