---
title: 建议的用于文档注释的 XML 标记 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: e59ee25b22c51e47dc83233af33099e6c55de87b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814934"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="c13ce-102">建议的用于文档注释的 XML 标记 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c13ce-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="c13ce-103">Visual Basic 编译器可以处理 XML 文件在代码中的文档注释。</span><span class="sxs-lookup"><span data-stu-id="c13ce-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="c13ce-104">可以使用其他工具来处理到文档中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="c13ce-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="c13ce-105">XML 注释类型等代码构造允许和类型成员。</span><span class="sxs-lookup"><span data-stu-id="c13ce-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="c13ce-106">分部类型只有一个部件类型的有 XML 注释，但没有注释其成员没有限制。</span><span class="sxs-lookup"><span data-stu-id="c13ce-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c13ce-107">文档注释不能应用于命名空间。</span><span class="sxs-lookup"><span data-stu-id="c13ce-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="c13ce-108">原因是一个命名空间可以跨多个程序集，并不是所有的程序集具有要同时加载。</span><span class="sxs-lookup"><span data-stu-id="c13ce-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="c13ce-109">编译器处理任何为有效的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="c13ce-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="c13ce-110">以下标记提供用户文档中的常用的功能。</span><span class="sxs-lookup"><span data-stu-id="c13ce-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="c13ce-111">\<c></span><span class="sxs-lookup"><span data-stu-id="c13ce-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="c13ce-112">\<code></span><span class="sxs-lookup"><span data-stu-id="c13ce-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="c13ce-113">\<example></span><span class="sxs-lookup"><span data-stu-id="c13ce-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="c13ce-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c13ce-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="c13ce-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c13ce-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="c13ce-116">\<list></span><span class="sxs-lookup"><span data-stu-id="c13ce-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="c13ce-117">\<para></span><span class="sxs-lookup"><span data-stu-id="c13ce-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="c13ce-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c13ce-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="c13ce-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="c13ce-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="c13ce-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c13ce-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="c13ce-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="c13ce-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="c13ce-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="c13ce-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="c13ce-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c13ce-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="c13ce-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c13ce-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="c13ce-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="c13ce-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="c13ce-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c13ce-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="c13ce-127">\<value></span><span class="sxs-lookup"><span data-stu-id="c13ce-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="c13ce-128">(<sup>1</sup>编译器验证语法。)</span><span class="sxs-lookup"><span data-stu-id="c13ce-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c13ce-129">如果你想的文档注释文本中显示尖括号，使用`&lt;`和`&gt;`。</span><span class="sxs-lookup"><span data-stu-id="c13ce-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="c13ce-130">例如，字符串`"&lt;text in angle brackets&gt;"`将显示为`<text in angle brackets>`。</span><span class="sxs-lookup"><span data-stu-id="c13ce-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13ce-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="c13ce-131">See also</span></span>

- [<span data-ttu-id="c13ce-132">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="c13ce-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="c13ce-133">/doc</span><span class="sxs-lookup"><span data-stu-id="c13ce-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="c13ce-134">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="c13ce-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
