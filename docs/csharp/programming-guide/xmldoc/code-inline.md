---
title: "&lt;c&gt;（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 21c7830c03b0b93e3597835954ac9e7d2feb49e9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcgt-c-programming-guide"></a><span data-ttu-id="60fd7-102">&lt;c&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="60fd7-102">&lt;c&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="60fd7-103">语法</span><span class="sxs-lookup"><span data-stu-id="60fd7-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60fd7-104">参数</span><span class="sxs-lookup"><span data-stu-id="60fd7-104">Parameters</span></span>  
 `text`  
 <span data-ttu-id="60fd7-105">要指示为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="60fd7-105">The text you would like to indicate as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60fd7-106">备注</span><span class="sxs-lookup"><span data-stu-id="60fd7-106">Remarks</span></span>  
 <span data-ttu-id="60fd7-107">使用 \<c> 标记可以指示应将说明内的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="60fd7-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="60fd7-108">使用 [\<code>](../../../csharp/programming-guide/xmldoc/code.md) 指示作为代码的多行文本。</span><span class="sxs-lookup"><span data-stu-id="60fd7-108">Use [\<code>](../../../csharp/programming-guide/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="60fd7-109">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="60fd7-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60fd7-110">示例</span><span class="sxs-lookup"><span data-stu-id="60fd7-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/code-inline_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="60fd7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60fd7-111">See Also</span></span>  
 [<span data-ttu-id="60fd7-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="60fd7-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="60fd7-113">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="60fd7-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
