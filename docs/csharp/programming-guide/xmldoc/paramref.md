---
title: "&lt;paramref&gt;（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fff532c02538f121ebe399e1780d8c19d9d6633a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltparamrefgt-c-programming-guide"></a><span data-ttu-id="d0f6a-102">&lt;paramref&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d0f6a-102">&lt;paramref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d0f6a-103">语法</span><span class="sxs-lookup"><span data-stu-id="d0f6a-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0f6a-104">参数</span><span class="sxs-lookup"><span data-stu-id="d0f6a-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d0f6a-105">要引用的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="d0f6a-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="d0f6a-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="d0f6a-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0f6a-107">备注</span><span class="sxs-lookup"><span data-stu-id="d0f6a-107">Remarks</span></span>  
 <span data-ttu-id="d0f6a-108">\<paramref> 标记提供一种方式，用于指示 \<summary> 或 \<remarks> 块等代码注释中的单词引用某个参数。</span><span class="sxs-lookup"><span data-stu-id="d0f6a-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="d0f6a-109">可以处理 XML 文件以明显的方式设置此单词的格式，如使用粗体或斜体。</span><span class="sxs-lookup"><span data-stu-id="d0f6a-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="d0f6a-110">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="d0f6a-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f6a-111">示例</span><span class="sxs-lookup"><span data-stu-id="d0f6a-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d0f6a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0f6a-112">See Also</span></span>  
 [<span data-ttu-id="d0f6a-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d0f6a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d0f6a-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="d0f6a-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
