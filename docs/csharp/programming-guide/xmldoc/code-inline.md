---
title: '&lt;c&gt; - C# 编程指南'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: b789b95c5e23534fb36613ac9203f146b265a98d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640974"
---
# <a name="ltcgt-c-programming-guide"></a><span data-ttu-id="fd361-102">&lt;c&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fd361-102">&lt;c&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="fd361-103">语法</span><span class="sxs-lookup"><span data-stu-id="fd361-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd361-104">参数</span><span class="sxs-lookup"><span data-stu-id="fd361-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="fd361-105">要指示为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="fd361-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd361-106">备注</span><span class="sxs-lookup"><span data-stu-id="fd361-106">Remarks</span></span>  
 <span data-ttu-id="fd361-107">使用 \<c> 标记可以指示应将说明内的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="fd361-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="fd361-108">使用 [\<code>](../../../csharp/programming-guide/xmldoc/code.md) 指示作为代码的多行文本。</span><span class="sxs-lookup"><span data-stu-id="fd361-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="fd361-109">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="fd361-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd361-110">示例</span><span class="sxs-lookup"><span data-stu-id="fd361-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fd361-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd361-111">See also</span></span>

- [<span data-ttu-id="fd361-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fd361-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fd361-113">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="fd361-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
