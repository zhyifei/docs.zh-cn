---
title: '&lt;see&gt;（C# 编程指南）'
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: c37ad869b3eb904377cd4470a85cd557f6560290
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44196356"
---
# <a name="ltseegt-c-programming-guide"></a><span data-ttu-id="8fa7a-102">&lt;see&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8fa7a-102">&lt;see&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8fa7a-103">语法</span><span class="sxs-lookup"><span data-stu-id="8fa7a-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fa7a-104">参数</span><span class="sxs-lookup"><span data-stu-id="8fa7a-104">Parameters</span></span>  
 <span data-ttu-id="8fa7a-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="8fa7a-105">cref = " `member`"</span></span>  
 <span data-ttu-id="8fa7a-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="8fa7a-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="8fa7a-107">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。将 member 放在双引号 (" ") 中。</span><span class="sxs-lookup"><span data-stu-id="8fa7a-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fa7a-108">备注</span><span class="sxs-lookup"><span data-stu-id="8fa7a-108">Remarks</span></span>  
 <span data-ttu-id="8fa7a-109">通过 \<see> 标记可以从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="8fa7a-109">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="8fa7a-110">使用 [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) 指示文本应该放在“另请参阅”部分中。</span><span class="sxs-lookup"><span data-stu-id="8fa7a-110">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="8fa7a-111">使用 [cref 属性](../../../csharp/programming-guide/xmldoc/cref-attribute.md)创建指向代码元素的文档页的内部超链接。</span><span class="sxs-lookup"><span data-stu-id="8fa7a-111">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="8fa7a-112">使用 [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="8fa7a-112">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="8fa7a-113">下面的示例展示摘要部分中的 \<see> 标记。</span><span class="sxs-lookup"><span data-stu-id="8fa7a-113">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8fa7a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fa7a-114">See Also</span></span>

- [<span data-ttu-id="8fa7a-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8fa7a-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8fa7a-116">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="8fa7a-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
