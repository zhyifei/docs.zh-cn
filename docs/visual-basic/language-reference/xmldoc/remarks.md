---
title: "&lt;备注&gt;(Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: c1b2c48dc3247935f703ff4107f29829c494a305
ms.contentlocale: zh-cn
ms.lasthandoff: 06/01/2017

---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="c1524-102">&lt;备注&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1524-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="c1524-103">指定成员的备注部分。</span><span class="sxs-lookup"><span data-stu-id="c1524-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1524-104">语法</span><span class="sxs-lookup"><span data-stu-id="c1524-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1524-105">参数</span><span class="sxs-lookup"><span data-stu-id="c1524-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="c1524-106">成员的说明。</span><span class="sxs-lookup"><span data-stu-id="c1524-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1524-107">备注</span><span class="sxs-lookup"><span data-stu-id="c1524-107">Remarks</span></span>  
 <span data-ttu-id="c1524-108">使用`<remarks>`标记以添加有关类型，使用指定的信息提供补充[\<摘要&1;>](../../../visual-basic/language-reference/xmldoc/summary.md)。</span><span class="sxs-lookup"><span data-stu-id="c1524-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="c1524-109">此信息显示在对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="c1524-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="c1524-110">对象浏览器有关的信息，请参阅[查看代码结构](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="c1524-110">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="c1524-111">使用编译[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)将文档注释处理到一个文件。</span><span class="sxs-lookup"><span data-stu-id="c1524-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1524-112">示例</span><span class="sxs-lookup"><span data-stu-id="c1524-112">Example</span></span>  
 <span data-ttu-id="c1524-113">此示例使用`<remarks>`标记解释`UpdateRecord`方法执行。</span><span class="sxs-lookup"><span data-stu-id="c1524-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 <span data-ttu-id="c1524-114">[!code-vb[VbVbcnXmlDocComments #&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c1524-114">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1524-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1524-115">See Also</span></span>  
 [<span data-ttu-id="c1524-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="c1524-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
