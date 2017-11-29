---
title: '&lt;paramref&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3bf3d4f04997a03f442cf7fd2a1586604198d3fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltparamrefgt-visual-basic"></a><span data-ttu-id="b76b0-102">&lt;paramref&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b76b0-102">&lt;paramref&gt; (Visual Basic)</span></span>
<span data-ttu-id="b76b0-103">将一个词格式化作为参数。</span><span class="sxs-lookup"><span data-stu-id="b76b0-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b76b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="b76b0-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b76b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="b76b0-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b76b0-106">要引用的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="b76b0-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="b76b0-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="b76b0-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b76b0-108">备注</span><span class="sxs-lookup"><span data-stu-id="b76b0-108">Remarks</span></span>  
 <span data-ttu-id="b76b0-109">`<paramref>`标记为你提供了一种方法，以指示词为参数。</span><span class="sxs-lookup"><span data-stu-id="b76b0-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="b76b0-110">可以处理 XML 文件，以设置此参数的格式以不同的方式。</span><span class="sxs-lookup"><span data-stu-id="b76b0-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="b76b0-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="b76b0-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b76b0-112">示例</span><span class="sxs-lookup"><span data-stu-id="b76b0-112">Example</span></span>  
 <span data-ttu-id="b76b0-113">此示例使用`<paramref>`标记来指代`id`参数。</span><span class="sxs-lookup"><span data-stu-id="b76b0-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/paramref_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b76b0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b76b0-114">See Also</span></span>  
 [<span data-ttu-id="b76b0-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="b76b0-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
