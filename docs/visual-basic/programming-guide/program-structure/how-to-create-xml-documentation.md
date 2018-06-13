---
title: 如何：在 Visual Basic 中创建 XML 文档
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650876"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="b6e25-102">如何：在 Visual Basic 中创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="b6e25-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="b6e25-103">此示例演示如何将 XML 文档注释添加到你的代码。</span><span class="sxs-lookup"><span data-stu-id="b6e25-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="b6e25-104">若要创建一个类型或成员的 XML 文档</span><span class="sxs-lookup"><span data-stu-id="b6e25-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="b6e25-105">在**代码编辑器**，放置在你想要创建文档的类型或成员上方的行的光标。</span><span class="sxs-lookup"><span data-stu-id="b6e25-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="b6e25-106">类型`'''`（三个单引号引起来）。</span><span class="sxs-lookup"><span data-stu-id="b6e25-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="b6e25-107">在中添加该类型或成员的 XML 主干**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="b6e25-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="b6e25-108">添加到相应的标记之间的描述性信息。</span><span class="sxs-lookup"><span data-stu-id="b6e25-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6e25-109">如果你添加的 XML 文档块中的其他行，每行必须以开头`'''`。</span><span class="sxs-lookup"><span data-stu-id="b6e25-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="b6e25-110">添加新的 XML 文档注释中使用该类型或成员的其他代码。</span><span class="sxs-lookup"><span data-stu-id="b6e25-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="b6e25-111">IntelliSense 会在显示中的文本\<摘要 > 标记的类型或成员。</span><span class="sxs-lookup"><span data-stu-id="b6e25-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="b6e25-112">编译代码，以生成包含文档注释的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b6e25-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="b6e25-113">有关详细信息，请参阅 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)。</span><span class="sxs-lookup"><span data-stu-id="b6e25-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e25-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6e25-114">See Also</span></span>  
 [<span data-ttu-id="b6e25-115">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="b6e25-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="b6e25-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="b6e25-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="b6e25-117">/doc</span><span class="sxs-lookup"><span data-stu-id="b6e25-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
