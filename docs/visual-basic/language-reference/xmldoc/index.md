---
title: 建议用于文档注释的 XML 标记
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 093c967557b899c8661fdec348d421996e948b94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352338"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="ca8ab-102">建议的用于文档注释的 XML 标记 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca8ab-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="ca8ab-103">Visual Basic 编译器可以在代码中将文档注释处理到 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="ca8ab-104">您可以使用其他工具将 XML 文件处理到文档中。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="ca8ab-105">允许对代码构造（如类型和类型成员）使用 XML 注释。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="ca8ab-106">对于分部类型，只有一个类型的部分可以有 XML 注释，尽管注释其成员没有限制。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca8ab-107">文档注释不能应用于命名空间。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="ca8ab-108">原因是一个命名空间可以跨多个程序集，而不是所有程序集都必须同时加载。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="ca8ab-109">编译器将处理任何为有效 XML 的标记。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="ca8ab-110">以下标记提供用户文档中的常用功能。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="ca8ab-111">\<c></span><span class="sxs-lookup"><span data-stu-id="ca8ab-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="ca8ab-112">\<code></span><span class="sxs-lookup"><span data-stu-id="ca8ab-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="ca8ab-113">\<example></span><span class="sxs-lookup"><span data-stu-id="ca8ab-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="ca8ab-114">[\<异常 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca8ab-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="ca8ab-115">[\<包括 >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca8ab-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="ca8ab-116">\<list></span><span class="sxs-lookup"><span data-stu-id="ca8ab-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="ca8ab-117">\<para></span><span class="sxs-lookup"><span data-stu-id="ca8ab-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="ca8ab-118">[\<参数 >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca8ab-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="ca8ab-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="ca8ab-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="ca8ab-120">[\<权限 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca8ab-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="ca8ab-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="ca8ab-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="ca8ab-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="ca8ab-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="ca8ab-123">[\<参阅 >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca8ab-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="ca8ab-124">[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca8ab-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="ca8ab-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="ca8ab-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="ca8ab-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca8ab-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="ca8ab-127">\<value></span><span class="sxs-lookup"><span data-stu-id="ca8ab-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="ca8ab-128">（<sup>1</sup>编译器验证语法。）</span><span class="sxs-lookup"><span data-stu-id="ca8ab-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca8ab-129">如果要在文档注释的文本中显示尖括号，请使用 `&lt;` 和 `&gt;`。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="ca8ab-130">例如，字符串 `"&lt;text in angle brackets&gt;"` 将显示为 `<text in angle brackets>`。</span><span class="sxs-lookup"><span data-stu-id="ca8ab-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca8ab-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca8ab-131">See also</span></span>

- [<span data-ttu-id="ca8ab-132">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="ca8ab-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="ca8ab-133">-doc</span><span class="sxs-lookup"><span data-stu-id="ca8ab-133">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="ca8ab-134">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="ca8ab-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
