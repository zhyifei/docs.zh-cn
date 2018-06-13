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
ms.openlocfilehash: f75e517890275b90523dc42cdac3a83d871beac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427197"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="0229b-102">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="0229b-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="0229b-103">表示由符号存储引用的文档。</span><span class="sxs-lookup"><span data-stu-id="0229b-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="0229b-104">文档由统一资源定位器 (URL) 和 GUID 的文档类型定义。</span><span class="sxs-lookup"><span data-stu-id="0229b-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="0229b-105">你可以查找而不考虑如何存储通过使用的 URL 的文档和文档类型 GUID。</span><span class="sxs-lookup"><span data-stu-id="0229b-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="0229b-106">你可以在符号存储区中存储的文档源，并通过此接口检索它。</span><span class="sxs-lookup"><span data-stu-id="0229b-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0229b-107">方法</span><span class="sxs-lookup"><span data-stu-id="0229b-107">Methods</span></span>  
  
|<span data-ttu-id="0229b-108">方法</span><span class="sxs-lookup"><span data-stu-id="0229b-108">Method</span></span>|<span data-ttu-id="0229b-109">描述</span><span class="sxs-lookup"><span data-stu-id="0229b-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0229b-110">FindClosestLine 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="0229b-111">是作为序列点的最近的一行中一行返回此文档中可能也可能不是序列点。</span><span class="sxs-lookup"><span data-stu-id="0229b-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="0229b-112">GetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="0229b-113">获取校验和。</span><span class="sxs-lookup"><span data-stu-id="0229b-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="0229b-114">GetCheckSumAlgorithmId 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="0229b-115">获取校验和算法标识符，或如果没有校验和，则返回全为零的 GUID。</span><span class="sxs-lookup"><span data-stu-id="0229b-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="0229b-116">GetDocumentType 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="0229b-117">获取此文档的文档类型。</span><span class="sxs-lookup"><span data-stu-id="0229b-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="0229b-118">GetLanguage 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="0229b-119">获取此文档的语言标识符。</span><span class="sxs-lookup"><span data-stu-id="0229b-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="0229b-120">GetLanguageVendor 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="0229b-121">获取此文档的语言供应商。</span><span class="sxs-lookup"><span data-stu-id="0229b-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="0229b-122">GetSourceLength 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="0229b-123">获取嵌入源的长度（以字节表示）。</span><span class="sxs-lookup"><span data-stu-id="0229b-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="0229b-124">GetSourceRange 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="0229b-125">返回到给定缓冲区中嵌入源的指定的范围。</span><span class="sxs-lookup"><span data-stu-id="0229b-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="0229b-126">GetURL 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="0229b-127">返回此文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="0229b-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="0229b-128">HasEmbeddedSource 方法</span><span class="sxs-lookup"><span data-stu-id="0229b-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="0229b-129">返回`true`如果该文档具有源嵌入在调试符号; 否则，返回`false`。</span><span class="sxs-lookup"><span data-stu-id="0229b-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0229b-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="0229b-130">See Also</span></span>  
 [<span data-ttu-id="0229b-131">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="0229b-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
