---
title: "&lt;代码&gt;(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7c1d8ab3db0c36c6a2935b9ffbef15e87df5ebc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltcodegt-visual-basic"></a><span data-ttu-id="63532-102">&lt;代码&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63532-102">&lt;code&gt; (Visual Basic)</span></span>
<span data-ttu-id="63532-103">指示该文本是多行代码。</span><span class="sxs-lookup"><span data-stu-id="63532-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63532-104">语法</span><span class="sxs-lookup"><span data-stu-id="63532-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63532-105">参数</span><span class="sxs-lookup"><span data-stu-id="63532-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="63532-106">要将标记为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="63532-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63532-107">备注</span><span class="sxs-lookup"><span data-stu-id="63532-107">Remarks</span></span>  
 <span data-ttu-id="63532-108">使用`<code>`标记以指示多行代码。</span><span class="sxs-lookup"><span data-stu-id="63532-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="63532-109">使用 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) 指示应将说明内的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="63532-109">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="63532-110">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="63532-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63532-111">示例</span><span class="sxs-lookup"><span data-stu-id="63532-111">Example</span></span>  
 <span data-ttu-id="63532-112">此示例使用\<代码 > 标记，包括示例代码使用`ID`字段。</span><span class="sxs-lookup"><span data-stu-id="63532-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="63532-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63532-113">See Also</span></span>  
 [<span data-ttu-id="63532-114">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="63532-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
