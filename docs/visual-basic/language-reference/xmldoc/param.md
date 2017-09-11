---
title: "&lt;param&gt; (Visual Basic 中) |Microsoft 文档"
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
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: ddf5baf83816d757edf67cdf1c66dc24e4313b83
ms.contentlocale: zh-cn
ms.lasthandoff: 06/01/2017

---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="69aef-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69aef-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="69aef-103">定义参数名称和说明。</span><span class="sxs-lookup"><span data-stu-id="69aef-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69aef-104">语法</span><span class="sxs-lookup"><span data-stu-id="69aef-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69aef-105">参数</span><span class="sxs-lookup"><span data-stu-id="69aef-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="69aef-106">方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="69aef-106">The name of a method parameter.</span></span> <span data-ttu-id="69aef-107">将名称括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="69aef-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="69aef-108">有关参数的说明。</span><span class="sxs-lookup"><span data-stu-id="69aef-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69aef-109">备注</span><span class="sxs-lookup"><span data-stu-id="69aef-109">Remarks</span></span>  
 <span data-ttu-id="69aef-110">`<param>`标记应当用于方法声明的注释，以描述一个方法的参数。</span><span class="sxs-lookup"><span data-stu-id="69aef-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="69aef-111">文本`<param>`标记将出现在以下位置︰</span><span class="sxs-lookup"><span data-stu-id="69aef-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="69aef-112">IntelliSense 的参数信息。</span><span class="sxs-lookup"><span data-stu-id="69aef-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="69aef-113">有关详细信息，请参阅[使用 IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)。</span><span class="sxs-lookup"><span data-stu-id="69aef-113">For more information, see [Using IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="69aef-114">对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="69aef-114">Object Browser.</span></span> <span data-ttu-id="69aef-115">有关详细信息，请参阅[查看代码的结构](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="69aef-115">For more information, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="69aef-116">使用编译[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)将文档注释处理到一个文件。</span><span class="sxs-lookup"><span data-stu-id="69aef-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69aef-117">示例</span><span class="sxs-lookup"><span data-stu-id="69aef-117">Example</span></span>  
 <span data-ttu-id="69aef-118">此示例使用`<param>`标记描述`id`参数。</span><span class="sxs-lookup"><span data-stu-id="69aef-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 <span data-ttu-id="69aef-119">[!code-vb[VbVbcnXmlDocComments #&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="69aef-119">[!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69aef-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69aef-120">See Also</span></span>  
 [<span data-ttu-id="69aef-121">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="69aef-121">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
