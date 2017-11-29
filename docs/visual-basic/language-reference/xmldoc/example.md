---
title: "&lt;示例&gt;(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e34b75f4ce924a35dd5396b449730316025a9f35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltexamplegt-visual-basic"></a><span data-ttu-id="59271-102">&lt;示例&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59271-102">&lt;example&gt; (Visual Basic)</span></span>
<span data-ttu-id="59271-103">指定成员的一个示例。</span><span class="sxs-lookup"><span data-stu-id="59271-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59271-104">语法</span><span class="sxs-lookup"><span data-stu-id="59271-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59271-105">参数</span><span class="sxs-lookup"><span data-stu-id="59271-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="59271-106">代码示例的说明。</span><span class="sxs-lookup"><span data-stu-id="59271-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59271-107">备注</span><span class="sxs-lookup"><span data-stu-id="59271-107">Remarks</span></span>  
 <span data-ttu-id="59271-108">`<example>`标记可以指定如何使用的方法或其他库成员的一个示例。</span><span class="sxs-lookup"><span data-stu-id="59271-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="59271-109">这通常涉及到使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 标记。</span><span class="sxs-lookup"><span data-stu-id="59271-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="59271-110">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="59271-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59271-111">示例</span><span class="sxs-lookup"><span data-stu-id="59271-111">Example</span></span>  
 <span data-ttu-id="59271-112">此示例使用`<example>`标记以包括一个示例，用于使用`ID`字段。</span><span class="sxs-lookup"><span data-stu-id="59271-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="59271-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59271-113">See Also</span></span>  
 [<span data-ttu-id="59271-114">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="59271-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
