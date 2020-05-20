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
ms.openlocfilehash: a8ff6d3a925773e58e0713a87b167420c246f85b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615561"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="5f65e-102">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="5f65e-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="5f65e-103">表示由符号存储引用的文档。</span><span class="sxs-lookup"><span data-stu-id="5f65e-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="5f65e-104">文档由统一资源定位器（URL）和文档类型 GUID 定义。</span><span class="sxs-lookup"><span data-stu-id="5f65e-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="5f65e-105">可以通过使用 URL 和文档类型 GUID 来查找文档，而不考虑其存储方式。</span><span class="sxs-lookup"><span data-stu-id="5f65e-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="5f65e-106">可以将文档源存储在符号存储区中，并通过此接口进行检索。</span><span class="sxs-lookup"><span data-stu-id="5f65e-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f65e-107">方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-107">Methods</span></span>  
  
|<span data-ttu-id="5f65e-108">方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-108">Method</span></span>|<span data-ttu-id="5f65e-109">说明</span><span class="sxs-lookup"><span data-stu-id="5f65e-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f65e-110">FindClosestLine 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="5f65e-111">如果此文档中的一行可能是也可能不是序列点，则返回作为序列点的最近行。</span><span class="sxs-lookup"><span data-stu-id="5f65e-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="5f65e-112">GetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="5f65e-113">获取校验和。</span><span class="sxs-lookup"><span data-stu-id="5f65e-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="5f65e-114">GetCheckSumAlgorithmId 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="5f65e-115">如果没有校验和，则获取校验和算法标识符，或返回所有零的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5f65e-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="5f65e-116">GetDocumentType 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="5f65e-117">获取此文档的文档类型。</span><span class="sxs-lookup"><span data-stu-id="5f65e-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="5f65e-118">GetLanguage 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="5f65e-119">获取此文档的语言标识符。</span><span class="sxs-lookup"><span data-stu-id="5f65e-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="5f65e-120">GetLanguageVendor 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="5f65e-121">获取此文档的语言供应商。</span><span class="sxs-lookup"><span data-stu-id="5f65e-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="5f65e-122">GetSourceLength 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="5f65e-123">获取嵌入源的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="5f65e-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="5f65e-124">GetSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="5f65e-125">将嵌入源的指定范围返回到给定缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="5f65e-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="5f65e-126">GetURL 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="5f65e-127">返回此文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="5f65e-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="5f65e-128">HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="5f65e-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="5f65e-129">`true`如果文档在调试符号中嵌入了源，则返回; 否则返回 `false` 。</span><span class="sxs-lookup"><span data-stu-id="5f65e-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f65e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f65e-130">See also</span></span>

- [<span data-ttu-id="5f65e-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="5f65e-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
