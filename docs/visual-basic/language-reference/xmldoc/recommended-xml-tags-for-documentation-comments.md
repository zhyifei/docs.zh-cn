---
title: "建议的文档注释 (Visual Basic 中) 的 XML 标记 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e4a6c3128a69e8d666d44882ef3eac9f9a31a51a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="13c60-102">建议的用于文档注释的 XML 标记 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13c60-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="13c60-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器可以处理你的代码与 XML 文件中的文档注释。</span><span class="sxs-lookup"><span data-stu-id="13c60-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="13c60-104">其他工具可用于 XML 文件处理成文档。</span><span class="sxs-lookup"><span data-stu-id="13c60-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="13c60-105">XML 注释可以在代码构造，如类型和类型成员。</span><span class="sxs-lookup"><span data-stu-id="13c60-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="13c60-106">对于分部类型只能有一个类型的一部分可以有 XML 注释，尽管没有对其成员的注释没有限制。</span><span class="sxs-lookup"><span data-stu-id="13c60-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c60-107">文档注释不能应用于命名空间。</span><span class="sxs-lookup"><span data-stu-id="13c60-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="13c60-108">原因是一个命名空间可以跨多个程序集，并不是所有程序集必须加载一次。</span><span class="sxs-lookup"><span data-stu-id="13c60-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="13c60-109">编译器会处理任何为有效的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="13c60-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="13c60-110">下列标记提供用户文档中的常用的功能。</span><span class="sxs-lookup"><span data-stu-id="13c60-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="13c60-111">\<c&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="13c60-112">\<代码&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="13c60-113">\<示例&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="13c60-114">[\<异常&1;>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13c60-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="13c60-115">[\<包括&1;>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13c60-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="13c60-116">\<list></span><span class="sxs-lookup"><span data-stu-id="13c60-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="13c60-117">\<para&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="13c60-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13c60-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="13c60-119">\<paramref&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="13c60-120">[\<权限&1;>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13c60-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="13c60-121">\<备注&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="13c60-122">\<返回&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="13c60-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13c60-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="13c60-124">[\<seealso&1;>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13c60-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="13c60-125">\<摘要&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="13c60-126">[\<typeparam&1;>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13c60-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="13c60-127">\<值&1;></span><span class="sxs-lookup"><span data-stu-id="13c60-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="13c60-128">(<sup>1</sup>编译器验证语法。)</span><span class="sxs-lookup"><span data-stu-id="13c60-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c60-129">如果要尖括号的文档注释文本中显示时，使用`<`和`>`。</span><span class="sxs-lookup"><span data-stu-id="13c60-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`.</span></span> <span data-ttu-id="13c60-130">例如，字符串`"<text in angle brackets>"`将显示为`<text in angle``brackets>`。</span><span class="sxs-lookup"><span data-stu-id="13c60-130">For example, the string `"<text in angle brackets>"` will appear as `<text in angle``brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c60-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13c60-131">See Also</span></span>  
 <span data-ttu-id="13c60-132">[使用 XML 将代码文档化](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="13c60-132">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="13c60-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span><span class="sxs-lookup"><span data-stu-id="13c60-133"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) </span></span>  
<span data-ttu-id="13c60-134"> [如何：创建 XML 文档](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span><span class="sxs-lookup"><span data-stu-id="13c60-134"> [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)</span></span>
