---
title: 建议的文档注释标记 - C# 编程指南
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: c746615d0d7a7a3058fbe2f8506a7a7c5c4a8779
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789728"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a><span data-ttu-id="5b92a-102">建议的文档注释标记（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5b92a-102">Recommended tags for documentation comments (C# programming guide)</span></span>

<span data-ttu-id="5b92a-103">C# 编译器处理代码中的文档注释，并在文件中将其设置为 XML 格式，该文件的名称通过 /doc 命令行选项指定  。</span><span class="sxs-lookup"><span data-stu-id="5b92a-103">The C# compiler processes documentation comments in your code and formats them as XML in a file whose name you specify in the **/doc** command-line option.</span></span> <span data-ttu-id="5b92a-104">若要基于编译器生成的文件创建最终文档，可以创建一个自定义工具，也可以使用 [DocFX](https://dotnet.github.io/docfx/) 或 [Sandcastle](https://github.com/EWSoftware/SHFB) 等工具。</span><span class="sxs-lookup"><span data-stu-id="5b92a-104">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="5b92a-105">在类型和类型成员等代码构造中处理标记。</span><span class="sxs-lookup"><span data-stu-id="5b92a-105">Tags are processed on code constructs such as types and type members.</span></span>

> [!NOTE]
> <span data-ttu-id="5b92a-106">不可对命名空间应用文档注释。</span><span class="sxs-lookup"><span data-stu-id="5b92a-106">Documentation comments cannot be applied to a namespace.</span></span>  
  
 <span data-ttu-id="5b92a-107">编译器将处理属于有效 XML 形式的任何标记。</span><span class="sxs-lookup"><span data-stu-id="5b92a-107">The compiler will process any tag that is valid XML.</span></span> <span data-ttu-id="5b92a-108">下列标记提供用户文档的中常用功能。</span><span class="sxs-lookup"><span data-stu-id="5b92a-108">The following tags provide generally used functionality in user documentation.</span></span>  
  
## <a name="tags"></a><span data-ttu-id="5b92a-109">Tags</span><span class="sxs-lookup"><span data-stu-id="5b92a-109">Tags</span></span>  
  
|||||  
|---|---|---|---|
|[<span data-ttu-id="5b92a-110">\<c></span><span class="sxs-lookup"><span data-stu-id="5b92a-110">\<c></span></span>](./code-inline.md)|[<span data-ttu-id="5b92a-111">\<para></span><span class="sxs-lookup"><span data-stu-id="5b92a-111">\<para></span></span>](./para.md)|<span data-ttu-id="5b92a-112">[\<see>](./see.md)\*</span><span class="sxs-lookup"><span data-stu-id="5b92a-112">[\<see>](./see.md)\*</span></span>|[<span data-ttu-id="5b92a-113">\<value></span><span class="sxs-lookup"><span data-stu-id="5b92a-113">\<value></span></span>](./value.md)  
|[<span data-ttu-id="5b92a-114">\<code></span><span class="sxs-lookup"><span data-stu-id="5b92a-114">\<code></span></span>](./code.md)|<span data-ttu-id="5b92a-115">[\<param>](./param.md)\*</span><span class="sxs-lookup"><span data-stu-id="5b92a-115">[\<param>](./param.md)\*</span></span>|<span data-ttu-id="5b92a-116">[\<seealso>](./seealso.md)\*</span><span class="sxs-lookup"><span data-stu-id="5b92a-116">[\<seealso>](./seealso.md)\*</span></span>|  
|[<span data-ttu-id="5b92a-117">\<example></span><span class="sxs-lookup"><span data-stu-id="5b92a-117">\<example></span></span>](./example.md)|[<span data-ttu-id="5b92a-118">\<paramref></span><span class="sxs-lookup"><span data-stu-id="5b92a-118">\<paramref></span></span>](./paramref.md)|[<span data-ttu-id="5b92a-119">\<summary></span><span class="sxs-lookup"><span data-stu-id="5b92a-119">\<summary></span></span>](./summary.md)|  
|<span data-ttu-id="5b92a-120">[\<exception>](./exception.md)\*</span><span class="sxs-lookup"><span data-stu-id="5b92a-120">[\<exception>](./exception.md)\*</span></span>|<span data-ttu-id="5b92a-121">[\<permission>](./permission.md)\*</span><span class="sxs-lookup"><span data-stu-id="5b92a-121">[\<permission>](./permission.md)\*</span></span>|<span data-ttu-id="5b92a-122">[\<typeparam>](./typeparam.md)\*</span><span class="sxs-lookup"><span data-stu-id="5b92a-122">[\<typeparam>](./typeparam.md)\*</span></span>|  
|<span data-ttu-id="5b92a-123">[\<include>](./include.md)\*</span><span class="sxs-lookup"><span data-stu-id="5b92a-123">[\<include>](./include.md)\*</span></span>|[<span data-ttu-id="5b92a-124">\<remarks></span><span class="sxs-lookup"><span data-stu-id="5b92a-124">\<remarks></span></span>](./remarks.md)|[<span data-ttu-id="5b92a-125">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="5b92a-125">\<typeparamref></span></span>](./typeparamref.md)|  
|[<span data-ttu-id="5b92a-126">\<list></span><span class="sxs-lookup"><span data-stu-id="5b92a-126">\<list></span></span>](./list.md)|[<span data-ttu-id="5b92a-127">\<inheritdoc></span><span class="sxs-lookup"><span data-stu-id="5b92a-127">\<inheritdoc></span></span>](./inheritdoc.md)|[<span data-ttu-id="5b92a-128">\<returns></span><span class="sxs-lookup"><span data-stu-id="5b92a-128">\<returns></span></span>](./returns.md)|
  
<span data-ttu-id="5b92a-129">（\* 表示编译器验证语法。）</span><span class="sxs-lookup"><span data-stu-id="5b92a-129">(\* denotes that the compiler verifies syntax.)</span></span>

<span data-ttu-id="5b92a-130">如果希望在文档注释的文本中显示尖括号，请使用 `<` 和 `>` 的 HTML 编码，分别为 `&lt;` 和 `&gt;`。</span><span class="sxs-lookup"><span data-stu-id="5b92a-130">If you want angle brackets to appear in the text of a documentation comment, use the HTML encoding of `<` and `>` which is `&lt;` and `&gt;` respectively.</span></span> <span data-ttu-id="5b92a-131">下面的示例对此编码进行了演示。</span><span class="sxs-lookup"><span data-stu-id="5b92a-131">This encoding is shown in the following example.</span></span>

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a><span data-ttu-id="5b92a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b92a-132">See also</span></span>

- [<span data-ttu-id="5b92a-133">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5b92a-133">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="5b92a-134">-doc（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="5b92a-134">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="5b92a-135">XML 文档注释</span><span class="sxs-lookup"><span data-stu-id="5b92a-135">XML documentation comments</span></span>](./index.md)
