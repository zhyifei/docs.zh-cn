---
title: "&lt;see&gt;（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 959da56269081ebee036c620e535185609c5bff3
ms.sourcegitcommit: c3ebb11a66e85a465c9ba2c42592222630b7ff9e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="88ae6-102">&lt;see&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="88ae6-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="88ae6-103">语法</span><span class="sxs-lookup"><span data-stu-id="88ae6-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88ae6-104">参数</span><span class="sxs-lookup"><span data-stu-id="88ae6-104">Parameters</span></span>  
 <span data-ttu-id="88ae6-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="88ae6-105">cref = " `member`"</span></span>  
 <span data-ttu-id="88ae6-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="88ae6-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="88ae6-107">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。将 member 放在双引号 (" ") 中。</span><span class="sxs-lookup"><span data-stu-id="88ae6-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88ae6-108">备注</span><span class="sxs-lookup"><span data-stu-id="88ae6-108">Remarks</span></span>  
 <span data-ttu-id="88ae6-109">通过 \<see> 标记可以从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="88ae6-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="88ae6-110">使用 [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) 指示文本应该放在“另请参阅”部分中。</span><span class="sxs-lookup"><span data-stu-id="88ae6-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="88ae6-111">使用 [cref 属性](../../../csharp/programming-guide/xmldoc/cref-attribute.md)创建指向代码元素的文档页的内部超链接。</span><span class="sxs-lookup"><span data-stu-id="88ae6-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="88ae6-112">使用 [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="88ae6-112">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="88ae6-113">下面的示例展示摘要部分中的 \<see> 标记。</span><span class="sxs-lookup"><span data-stu-id="88ae6-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="88ae6-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="88ae6-114">See Also</span></span>  
 [<span data-ttu-id="88ae6-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="88ae6-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="88ae6-116">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="88ae6-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
