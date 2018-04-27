---
title: 建议的用于文档注释的 XML 标记 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7815d4c9fddc4e760c7495ef7a2509c55141e96e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="85872-102">建议的用于文档注释的 XML 标记 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85872-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="85872-103">Visual Basic 编译器可以处理你的代码的 XML 文件中的文档注释。</span><span class="sxs-lookup"><span data-stu-id="85872-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="85872-104">其他工具可用于文档处理 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="85872-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="85872-105">XML 注释允许在如类型的代码构造和类型成员。</span><span class="sxs-lookup"><span data-stu-id="85872-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="85872-106">分部类型，只有一个类型的一部分有 XML 注释，但没有注释其成员不受限制。</span><span class="sxs-lookup"><span data-stu-id="85872-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85872-107">文档注释不能应用于命名空间。</span><span class="sxs-lookup"><span data-stu-id="85872-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="85872-108">原因是一个命名空间可跨越多个程序集，并且不是所有程序集具有要同时加载。</span><span class="sxs-lookup"><span data-stu-id="85872-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="85872-109">编译器处理任何为有效的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="85872-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="85872-110">以下标记提供用户文档中的常用的功能。</span><span class="sxs-lookup"><span data-stu-id="85872-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="85872-111">\<c></span><span class="sxs-lookup"><span data-stu-id="85872-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="85872-112">\<code></span><span class="sxs-lookup"><span data-stu-id="85872-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="85872-113">\<example></span><span class="sxs-lookup"><span data-stu-id="85872-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="85872-114">[\<异常 >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85872-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="85872-115">[\<包括 >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85872-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="85872-116">\<list></span><span class="sxs-lookup"><span data-stu-id="85872-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="85872-117">\<para></span><span class="sxs-lookup"><span data-stu-id="85872-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="85872-118">[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85872-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="85872-119">\<paramref></span><span class="sxs-lookup"><span data-stu-id="85872-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="85872-120">[\<权限 >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85872-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="85872-121">\<remarks></span><span class="sxs-lookup"><span data-stu-id="85872-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="85872-122">\<returns></span><span class="sxs-lookup"><span data-stu-id="85872-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="85872-123">[\<请参阅 >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85872-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="85872-124">[\<另请参阅 >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85872-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="85872-125">\<summary></span><span class="sxs-lookup"><span data-stu-id="85872-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="85872-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85872-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="85872-127">\<value></span><span class="sxs-lookup"><span data-stu-id="85872-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="85872-128">(<sup>1</sup>编译器验证语法。)</span><span class="sxs-lookup"><span data-stu-id="85872-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85872-129">如果你希望命令的尖括号显示的文档注释的文本中，使用`<`和`>`。</span><span class="sxs-lookup"><span data-stu-id="85872-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="85872-130">例如，在字符串`"<text in angle brackets>"`将显示为`<text in angle``brackets>`。</span><span class="sxs-lookup"><span data-stu-id="85872-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85872-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="85872-131">See Also</span></span>  
 [<span data-ttu-id="85872-132">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="85872-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="85872-133">/doc</span><span class="sxs-lookup"><span data-stu-id="85872-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="85872-134">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="85872-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
