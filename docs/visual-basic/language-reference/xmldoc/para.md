---
title: '&lt;para&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e2a034974ed94b18da374fbd372063ea4d575440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="16d31-102">&lt;para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16d31-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="16d31-103">指定内容将格式化为一个段落。</span><span class="sxs-lookup"><span data-stu-id="16d31-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d31-104">语法</span><span class="sxs-lookup"><span data-stu-id="16d31-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16d31-105">参数</span><span class="sxs-lookup"><span data-stu-id="16d31-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="16d31-106">段落文本。</span><span class="sxs-lookup"><span data-stu-id="16d31-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16d31-107">备注</span><span class="sxs-lookup"><span data-stu-id="16d31-107">Remarks</span></span>  
 <span data-ttu-id="16d31-108">`<para>`标记是用于标记内，例如[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)， [\<备注 >](../../../visual-basic/language-reference/xmldoc/remarks.md)，或[\<返回 >](../../../visual-basic/language-reference/xmldoc/returns.md)，并允许您向文本添加结构。</span><span class="sxs-lookup"><span data-stu-id="16d31-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="16d31-109">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="16d31-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16d31-110">示例</span><span class="sxs-lookup"><span data-stu-id="16d31-110">Example</span></span>  
 <span data-ttu-id="16d31-111">此示例使用`<para>`拆分的备注部分的标记`UpdateRecord`为两个段落的方法。</span><span class="sxs-lookup"><span data-stu-id="16d31-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="16d31-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16d31-112">See Also</span></span>  
 [<span data-ttu-id="16d31-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="16d31-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
