---
title: "&lt;see&gt;（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <see>
- see
dev_langs:
- CSharp
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 831caae9574c25f16e8b2ede734746f48019198e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="6bc00-102">&lt;see&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="6bc00-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="6bc00-103">语法</span><span class="sxs-lookup"><span data-stu-id="6bc00-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bc00-104">参数</span><span class="sxs-lookup"><span data-stu-id="6bc00-104">Parameters</span></span>  
 <span data-ttu-id="6bc00-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="6bc00-105">cref = " `member`"</span></span>  
 <span data-ttu-id="6bc00-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="6bc00-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="6bc00-107">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。将 member 放在双引号 (" ") 中。</span><span class="sxs-lookup"><span data-stu-id="6bc00-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bc00-108">备注</span><span class="sxs-lookup"><span data-stu-id="6bc00-108">Remarks</span></span>  
 <span data-ttu-id="6bc00-109">通过 \<see> 标记可以从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="6bc00-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="6bc00-110">使用 [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) 指示文本应该放在“另请参阅”部分中。</span><span class="sxs-lookup"><span data-stu-id="6bc00-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="6bc00-111">使用 [cref 属性](../../../csharp/programming-guide/xmldoc/cref-attribute.md)创建指向代码元素的文档页的内部超链接。</span><span class="sxs-lookup"><span data-stu-id="6bc00-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="6bc00-112">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="6bc00-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="6bc00-113">下面的示例展示摘要部分中的 \<see> 标记。</span><span class="sxs-lookup"><span data-stu-id="6bc00-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 <span data-ttu-id="6bc00-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6bc00-114">[!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc00-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bc00-115">See Also</span></span>  
 <span data-ttu-id="6bc00-116">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6bc00-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="6bc00-117">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="6bc00-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

