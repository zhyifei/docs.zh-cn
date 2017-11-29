---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b654fe6fc93642693730256b523fee999aa55937
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="ddabe-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ddabe-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="ddabe-103">定义的类型参数的名称和描述。</span><span class="sxs-lookup"><span data-stu-id="ddabe-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddabe-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddabe-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddabe-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddabe-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ddabe-106">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="ddabe-106">The name of the type parameter.</span></span> <span data-ttu-id="ddabe-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="ddabe-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="ddabe-108">类型参数的说明。</span><span class="sxs-lookup"><span data-stu-id="ddabe-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddabe-109">备注</span><span class="sxs-lookup"><span data-stu-id="ddabe-109">Remarks</span></span>  
 <span data-ttu-id="ddabe-110">使用`<typeparam>`用于泛型类型或泛型成员声明以描述一个类型参数的注释中的标记。</span><span class="sxs-lookup"><span data-stu-id="ddabe-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="ddabe-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="ddabe-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddabe-112">示例</span><span class="sxs-lookup"><span data-stu-id="ddabe-112">Example</span></span>  
 <span data-ttu-id="ddabe-113">此示例使用`<typeparam>`标记来描述`id`参数。</span><span class="sxs-lookup"><span data-stu-id="ddabe-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ddabe-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddabe-114">See Also</span></span>  
 [<span data-ttu-id="ddabe-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="ddabe-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
