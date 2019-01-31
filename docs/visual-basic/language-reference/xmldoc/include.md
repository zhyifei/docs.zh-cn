---
title: <include> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: ea14cc8182b8917a0805fbc509a0000c6df67462
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267035"
---
# <a name="include-visual-basic"></a><span data-ttu-id="fd331-102">\<包括 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd331-102">\<include> (Visual Basic)</span></span>
<span data-ttu-id="fd331-103">表示描述的类型和成员在源代码中的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="fd331-103">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd331-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd331-104">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd331-105">参数</span><span class="sxs-lookup"><span data-stu-id="fd331-105">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="fd331-106">必需。</span><span class="sxs-lookup"><span data-stu-id="fd331-106">Required.</span></span> <span data-ttu-id="fd331-107">包含文档的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="fd331-107">The name of the file containing the documentation.</span></span> <span data-ttu-id="fd331-108">可使用路径来限定文件名。</span><span class="sxs-lookup"><span data-stu-id="fd331-108">The file name can be qualified with a path.</span></span> <span data-ttu-id="fd331-109">将`filename`在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="fd331-109">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="fd331-110">必需。</span><span class="sxs-lookup"><span data-stu-id="fd331-110">Required.</span></span> <span data-ttu-id="fd331-111">`filename` 中标记的路径，它指向标记 `name`。</span><span class="sxs-lookup"><span data-stu-id="fd331-111">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="fd331-112">将该路径括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="fd331-112">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="fd331-113">必需。</span><span class="sxs-lookup"><span data-stu-id="fd331-113">Required.</span></span> <span data-ttu-id="fd331-114">中位于注释前的标记的名称说明符。</span><span class="sxs-lookup"><span data-stu-id="fd331-114">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="fd331-115">`Name` 将具有`id`。</span><span class="sxs-lookup"><span data-stu-id="fd331-115">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="fd331-116">必需。</span><span class="sxs-lookup"><span data-stu-id="fd331-116">Required.</span></span> <span data-ttu-id="fd331-117">标记的 ID（位于注释之前）。</span><span class="sxs-lookup"><span data-stu-id="fd331-117">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="fd331-118">将 ID 括在单引号 (' ')。</span><span class="sxs-lookup"><span data-stu-id="fd331-118">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd331-119">备注</span><span class="sxs-lookup"><span data-stu-id="fd331-119">Remarks</span></span>  
 <span data-ttu-id="fd331-120">使用`<include>`标记引用另一个文件中描述的类型的注释和你的源代码中的成员。</span><span class="sxs-lookup"><span data-stu-id="fd331-120">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="fd331-121">这是对直接在源代码文件中放入文档注释的替代方法。</span><span class="sxs-lookup"><span data-stu-id="fd331-121">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="fd331-122">`<include>`标记使用 W3C XML 路径语言 (XPath) 1.0 版建议。</span><span class="sxs-lookup"><span data-stu-id="fd331-122">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="fd331-123">详细了解如何自定义你`<include>`使用，请参阅<https://www.w3.org/TR/xpath>。</span><span class="sxs-lookup"><span data-stu-id="fd331-123">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd331-124">示例</span><span class="sxs-lookup"><span data-stu-id="fd331-124">Example</span></span>  
 <span data-ttu-id="fd331-125">此示例使用`<include>`标记从名为的文件导入成员文档注释`commentFile.xml`。</span><span class="sxs-lookup"><span data-stu-id="fd331-125">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 <span data-ttu-id="fd331-126">格式`commentFile.xml`如下所示。</span><span class="sxs-lookup"><span data-stu-id="fd331-126">The format of the `commentFile.xml` is as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd331-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd331-127">See also</span></span>
- [<span data-ttu-id="fd331-128">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="fd331-128">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
