---
title: "&lt;摘要&gt;(Visual Basic 中) |Microsoft 文档"
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
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
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
ms.openlocfilehash: 42321daf092c4b637d2f75fb7f6d7e95201791ba
ms.contentlocale: zh-cn
ms.lasthandoff: 06/01/2017

---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="32e96-102">&lt;摘要&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32e96-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="32e96-103">指定该成员的摘要。</span><span class="sxs-lookup"><span data-stu-id="32e96-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e96-104">语法</span><span class="sxs-lookup"><span data-stu-id="32e96-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="32e96-105">参数</span><span class="sxs-lookup"><span data-stu-id="32e96-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="32e96-106">对象的摘要。</span><span class="sxs-lookup"><span data-stu-id="32e96-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32e96-107">备注</span><span class="sxs-lookup"><span data-stu-id="32e96-107">Remarks</span></span>  
 <span data-ttu-id="32e96-108">使用`<summary>`标记来描述一个类型或类型成员。</span><span class="sxs-lookup"><span data-stu-id="32e96-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="32e96-109">使用[\<备注&1;>](../../../visual-basic/language-reference/xmldoc/remarks.md)将补充信息添加到类型说明。</span><span class="sxs-lookup"><span data-stu-id="32e96-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="32e96-110">文本`<summary>`标签是在 IntelliSense 中，类型信息的唯一源，它还会显示在对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="32e96-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="32e96-111">对象浏览器有关的信息，请参阅[查看代码结构](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="32e96-111">For information about the Object Browser, see [Viewing the Structure of Code](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="32e96-112">使用编译[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)将文档注释处理到一个文件。</span><span class="sxs-lookup"><span data-stu-id="32e96-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32e96-113">示例</span><span class="sxs-lookup"><span data-stu-id="32e96-113">Example</span></span>  
 <span data-ttu-id="32e96-114">此示例使用`<summary>`标记描述`ResetCounter`方法和`Counter`属性。</span><span class="sxs-lookup"><span data-stu-id="32e96-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 <span data-ttu-id="32e96-115">[!code-vb[VbVbcnXmlDocComments #&1;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="32e96-115">[!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32e96-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32e96-116">See Also</span></span>  
 [<span data-ttu-id="32e96-117">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="32e96-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
