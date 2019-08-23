---
title: 如何：在 Visual Basic 中创建 XML 文档
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 9380c23ab6cfdbecd519926229b45ed863f07f9e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947718"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="30daf-102">如何：在 Visual Basic 中创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="30daf-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="30daf-103">此示例演示如何将 XML 文档注释添加到代码。</span><span class="sxs-lookup"><span data-stu-id="30daf-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="30daf-104">为类型或成员创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="30daf-104">To create XML documentation for a type or member</span></span>  
  
1. <span data-ttu-id="30daf-105">在**代码编辑器**中, 将光标置于要为其创建文档的类型或成员之上的行上。</span><span class="sxs-lookup"><span data-stu-id="30daf-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2. <span data-ttu-id="30daf-106">键入`'''` (三个单引号)。</span><span class="sxs-lookup"><span data-stu-id="30daf-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="30daf-107">类型或成员的 XML 主干将添加到**代码编辑器**中。</span><span class="sxs-lookup"><span data-stu-id="30daf-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3. <span data-ttu-id="30daf-108">在适当的标记之间添加描述性信息。</span><span class="sxs-lookup"><span data-stu-id="30daf-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="30daf-109">如果在 XML 文档块中添加额外的行, 则每行都必须`'''`以开头。</span><span class="sxs-lookup"><span data-stu-id="30daf-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4. <span data-ttu-id="30daf-110">使用新的 XML 文档注释添加使用类型或成员的附加代码。</span><span class="sxs-lookup"><span data-stu-id="30daf-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="30daf-111">IntelliSense 将显示该类型或\<成员的 "摘要 >" 标记中的文本。</span><span class="sxs-lookup"><span data-stu-id="30daf-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5. <span data-ttu-id="30daf-112">编译代码以生成包含文档注释的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="30daf-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="30daf-113">有关详细信息，请参阅 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)。</span><span class="sxs-lookup"><span data-stu-id="30daf-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30daf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="30daf-114">See also</span></span>

- [<span data-ttu-id="30daf-115">使用 XML 记录代码</span><span class="sxs-lookup"><span data-stu-id="30daf-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="30daf-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="30daf-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="30daf-117">/doc</span><span class="sxs-lookup"><span data-stu-id="30daf-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
