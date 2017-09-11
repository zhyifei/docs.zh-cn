---
title: "如何︰ 在 Visual Basic 中创建 XML 文档 |Microsoft 文档"
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
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 3171877f4fa1913b5535d71d671cea97b5a22850
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="ed8f5-102">如何：在 Visual Basic 中创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="ed8f5-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="ed8f5-103">此示例演示如何将 XML 文档注释添加到您的代码。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="ed8f5-104">若要创建的类型或成员的 XML 文档</span><span class="sxs-lookup"><span data-stu-id="ed8f5-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="ed8f5-105">在**代码编辑器**，将鼠标光标放置在上方你想要创建文档的类型或成员的行。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="ed8f5-106">类型`'''`（三个单引号）。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="ed8f5-107">在添加该类型或成员的 XML 主干**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="ed8f5-108">添加相应的标记之间的描述性信息。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ed8f5-109">如果您添加的 XML 文档块内的其他行，每行必须以与`'''`。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="ed8f5-110">添加新的 XML 文档注释中使用该类型或成员的附加代码。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="ed8f5-111">IntelliSense 显示中的文本\<摘要&1;> 标记的类型或成员。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="ed8f5-112">编译代码以生成包含文档注释的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="ed8f5-113">有关详细信息，请参阅[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8f5-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8f5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed8f5-114">See Also</span></span>  
 <span data-ttu-id="ed8f5-115">[使用 XML 将代码文档化](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f5-115">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="ed8f5-116"> [XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="ed8f5-116"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="ed8f5-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span><span class="sxs-lookup"><span data-stu-id="ed8f5-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span></span>
