---
title: 建议的文档注释标记 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: a6d07b6c288ebbe24c9cf5c531ef333946855f82
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204712"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="a7dcb-102">建议的文档注释标记（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a7dcb-102">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="a7dcb-103">C# 编译器处理代码中的文档注释，并在文件中将其设置为 XML 格式，该文件的名称通过 /doc 命令行选项指定。</span><span class="sxs-lookup"><span data-stu-id="a7dcb-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="a7dcb-104">若要基于编译器生成的文件创建最终文档，可以创建一个自定义工具，也可以使用 [DocFX](https://dotnet.github.io/docfx/) 或 [Sandcastle](https://github.com/EWSoftware/SHFB) 等工具。</span><span class="sxs-lookup"><span data-stu-id="a7dcb-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="a7dcb-105">在类型和类型成员等代码构造中处理标记。</span><span class="sxs-lookup"><span data-stu-id="a7dcb-105">Tags are processed on code constructs such as types and type members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7dcb-106">不可对命名空间应用文档注释。</span><span class="sxs-lookup"><span data-stu-id="a7dcb-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="a7dcb-107">编译器将处理属于有效 XML 形式的任何标记。</span><span class="sxs-lookup"><span data-stu-id="a7dcb-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="a7dcb-108">下列标记提供用户文档的中常用功能。</span><span class="sxs-lookup"><span data-stu-id="a7dcb-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="a7dcb-109">Tags</span><span class="sxs-lookup"><span data-stu-id="a7dcb-109">Tags</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="a7dcb-110">\<c></span><span class="sxs-lookup"><span data-stu-id="a7dcb-110">\<c></span></span>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[<span data-ttu-id="a7dcb-111">\<para></span><span class="sxs-lookup"><span data-stu-id="a7dcb-111">\<para></span></span>](../../../csharp/programming-guide/xmldoc/para.md)|<span data-ttu-id="a7dcb-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span><span class="sxs-lookup"><span data-stu-id="a7dcb-112">[\<see>](../../../csharp/programming-guide/xmldoc/see.md)\*</span></span>|  
|[<span data-ttu-id="a7dcb-113">\<code></span><span class="sxs-lookup"><span data-stu-id="a7dcb-113">\<code></span></span>](../../../csharp/programming-guide/xmldoc/code.md)|<span data-ttu-id="a7dcb-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span><span class="sxs-lookup"><span data-stu-id="a7dcb-114">[\<param>](../../../csharp/programming-guide/xmldoc/param.md)\*</span></span>|<span data-ttu-id="a7dcb-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="a7dcb-115">[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)\*</span></span>|  
|[<span data-ttu-id="a7dcb-116">\<example></span><span class="sxs-lookup"><span data-stu-id="a7dcb-116">\<example></span></span>](../../../csharp/programming-guide/xmldoc/example.md)|[<span data-ttu-id="a7dcb-117">\<paramref></span><span class="sxs-lookup"><span data-stu-id="a7dcb-117">\<paramref></span></span>](../../../csharp/programming-guide/xmldoc/paramref.md)|[<span data-ttu-id="a7dcb-118">\<summary></span><span class="sxs-lookup"><span data-stu-id="a7dcb-118">\<summary></span></span>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|<span data-ttu-id="a7dcb-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="a7dcb-119">[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)\*</span></span>|<span data-ttu-id="a7dcb-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="a7dcb-120">[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)\*</span></span>|<span data-ttu-id="a7dcb-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="a7dcb-121">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*</span></span>|  
|<span data-ttu-id="a7dcb-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span><span class="sxs-lookup"><span data-stu-id="a7dcb-122">[\<include>](../../../csharp/programming-guide/xmldoc/include.md)\*</span></span>|[<span data-ttu-id="a7dcb-123">\<remarks></span><span class="sxs-lookup"><span data-stu-id="a7dcb-123">\<remarks></span></span>](../../../csharp/programming-guide/xmldoc/remarks.md)|[<span data-ttu-id="a7dcb-124">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="a7dcb-124">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[<span data-ttu-id="a7dcb-125">\<list></span><span class="sxs-lookup"><span data-stu-id="a7dcb-125">\<list></span></span>](../../../csharp/programming-guide/xmldoc/list.md)|[<span data-ttu-id="a7dcb-126">\<returns></span><span class="sxs-lookup"><span data-stu-id="a7dcb-126">\<returns></span></span>](../../../csharp/programming-guide/xmldoc/returns.md)|[<span data-ttu-id="a7dcb-127">\<value></span><span class="sxs-lookup"><span data-stu-id="a7dcb-127">\<value></span></span>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 <span data-ttu-id="a7dcb-128">（\* 表示编译器验证语法。）</span><span class="sxs-lookup"><span data-stu-id="a7dcb-128">(\* denotes that the compiler verifies syntax.)</span></span>  
  
 <span data-ttu-id="a7dcb-129">如果希望在文档注释的文本中显示尖括号，请使用 `<` 和 `>`，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="a7dcb-129">If you want angle brackets to appear in the text of a documentation comment, use `<` and `>`, as shown in the following example.</span></span>  
  
```csharp  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7dcb-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7dcb-130">See also</span></span>

- [<span data-ttu-id="a7dcb-131">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a7dcb-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a7dcb-132">/doc（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="a7dcb-132">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="a7dcb-133">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="a7dcb-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
