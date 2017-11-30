---
title: "&lt;包括&gt;(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22eebaa8da8ef082e132cfdf8cb68498bfe16d73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltincludegt-visual-basic"></a><span data-ttu-id="583fa-102">&lt;包括&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="583fa-102">&lt;include&gt; (Visual Basic)</span></span>
<span data-ttu-id="583fa-103">是指描述的类型和成员在源代码中的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="583fa-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="583fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="583fa-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="583fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="583fa-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="583fa-106">必需。</span><span class="sxs-lookup"><span data-stu-id="583fa-106">Required.</span></span> <span data-ttu-id="583fa-107">包含文档的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="583fa-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="583fa-108">可使用路径来限定文件名。</span><span class="sxs-lookup"><span data-stu-id="583fa-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="583fa-109">括起`filename`在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="583fa-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="583fa-110">必需。</span><span class="sxs-lookup"><span data-stu-id="583fa-110">Required.</span></span> <span data-ttu-id="583fa-111">`filename` 中标记的路径，它指向标记 `name`。</span><span class="sxs-lookup"><span data-stu-id="583fa-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="583fa-112">将路径括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="583fa-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="583fa-113">必需。</span><span class="sxs-lookup"><span data-stu-id="583fa-113">Required.</span></span> <span data-ttu-id="583fa-114">名称的说明符之前注释的标记中。</span><span class="sxs-lookup"><span data-stu-id="583fa-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="583fa-115">`Name`将具有`id`。</span><span class="sxs-lookup"><span data-stu-id="583fa-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="583fa-116">必需。</span><span class="sxs-lookup"><span data-stu-id="583fa-116">Required.</span></span> <span data-ttu-id="583fa-117">标记的 ID（位于注释之前）。</span><span class="sxs-lookup"><span data-stu-id="583fa-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="583fa-118">将此 ID 括在单引号 (' ')。</span><span class="sxs-lookup"><span data-stu-id="583fa-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="583fa-119">备注</span><span class="sxs-lookup"><span data-stu-id="583fa-119">Remarks</span></span>  
 <span data-ttu-id="583fa-120">使用`<include>`标记来引用另一个文件中的注释，用于描述的类型和成员在源代码中的。</span><span class="sxs-lookup"><span data-stu-id="583fa-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="583fa-121">这是对直接在源代码文件中放入文档注释的替代方法。</span><span class="sxs-lookup"><span data-stu-id="583fa-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="583fa-122">`<include>`标记使用 W3C XML 路径语言 (XPath) 1.0 版建议。</span><span class="sxs-lookup"><span data-stu-id="583fa-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="583fa-123">有关用于自定义的方法的详细信息你`<include>`使用位于 http://www.w3.org/TR/xpath。</span><span class="sxs-lookup"><span data-stu-id="583fa-123">More information for ways to customize your `<include>` use is available at http://www.w3.org/TR/xpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="583fa-124">示例</span><span class="sxs-lookup"><span data-stu-id="583fa-124">Example</span></span>  
 <span data-ttu-id="583fa-125">此示例使用`<include>`要从名为的文件导入成员文档注释标记`commentFile.xml`。</span><span class="sxs-lookup"><span data-stu-id="583fa-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="583fa-126">格式`commentFile.xml`如下。</span><span class="sxs-lookup"><span data-stu-id="583fa-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="583fa-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="583fa-127">See Also</span></span>  
 [<span data-ttu-id="583fa-128">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="583fa-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
