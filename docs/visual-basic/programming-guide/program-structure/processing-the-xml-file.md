---
title: 处理 XML 文件 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 6be7597f1c03d8aa044eba70ef6287cfc07d9b84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652033"
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="fc1c3-102">处理 XML 文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc1c3-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="fc1c3-103">编译器为代码（已标记以生成文档）中的每个构造生成一个 ID 字符串。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="fc1c3-104">(有关如何标记代码的信息，请参阅[XML 注释标记](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)。)ID 字符串唯一标识构造。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="fc1c3-105">处理 XML 文件的程序可以使用的 ID 字符串以标识相应[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]元数据/反射项。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-105">Programs that process the XML file can use the ID string to identify the corresponding [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] metadata/reflection item.</span></span>  
  
 <span data-ttu-id="fc1c3-106">XML 文件不是代码的你; 分层表示形式它是与每个元素的生成 ID 的平面列表。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="fc1c3-107">编译器在生成 ID 字符串时应遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="fc1c3-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
-   <span data-ttu-id="fc1c3-108">在字符串中不放置任何空格。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-108">No white space is placed in the string.</span></span>  
  
-   <span data-ttu-id="fc1c3-109">ID 字符串的第一部分标识的标识，与单个字符跟一个冒号的成员的类型。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="fc1c3-110">使用以下成员类型。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="fc1c3-111">字符</span><span class="sxs-lookup"><span data-stu-id="fc1c3-111">Character</span></span>|<span data-ttu-id="fc1c3-112">描述</span><span class="sxs-lookup"><span data-stu-id="fc1c3-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="fc1c3-113">N</span><span class="sxs-lookup"><span data-stu-id="fc1c3-113">N</span></span>|<span data-ttu-id="fc1c3-114">namespace</span><span class="sxs-lookup"><span data-stu-id="fc1c3-114">namespace</span></span><br /><br /> <span data-ttu-id="fc1c3-115">无法将文档注释添加到命名空间中，但可以对它们的 CREF 引用支持的位置。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="fc1c3-116">T</span><span class="sxs-lookup"><span data-stu-id="fc1c3-116">T</span></span>|<span data-ttu-id="fc1c3-117">类型： `Class`， `Module`， `Interface`， `Structure`， `Enum`， `Delegate`</span><span class="sxs-lookup"><span data-stu-id="fc1c3-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="fc1c3-118">F</span><span class="sxs-lookup"><span data-stu-id="fc1c3-118">F</span></span>|<span data-ttu-id="fc1c3-119">字段： `Dim`</span><span class="sxs-lookup"><span data-stu-id="fc1c3-119">field: `Dim`</span></span>|  
|<span data-ttu-id="fc1c3-120">P</span><span class="sxs-lookup"><span data-stu-id="fc1c3-120">P</span></span>|<span data-ttu-id="fc1c3-121">属性： `Property` （包括默认属性）</span><span class="sxs-lookup"><span data-stu-id="fc1c3-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="fc1c3-122">M</span><span class="sxs-lookup"><span data-stu-id="fc1c3-122">M</span></span>|<span data-ttu-id="fc1c3-123">方法： `Sub`， `Function`， `Declare`， `Operator`</span><span class="sxs-lookup"><span data-stu-id="fc1c3-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="fc1c3-124">E</span><span class="sxs-lookup"><span data-stu-id="fc1c3-124">E</span></span>|<span data-ttu-id="fc1c3-125">事件： `Event`</span><span class="sxs-lookup"><span data-stu-id="fc1c3-125">event: `Event`</span></span>|  
|<span data-ttu-id="fc1c3-126">!</span><span class="sxs-lookup"><span data-stu-id="fc1c3-126">!</span></span>|<span data-ttu-id="fc1c3-127">错误字符串</span><span class="sxs-lookup"><span data-stu-id="fc1c3-127">error string</span></span><br /><br /> <span data-ttu-id="fc1c3-128">字符串的其余部分提供有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="fc1c3-129">Visual Basic 编译器会生成无法解析的链接信息时出错。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span></span>|  
  
-   <span data-ttu-id="fc1c3-130">第二部分`String`是项，在命名空间的根目录的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="fc1c3-131">用句点分隔的项、 其封闭类型和命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="fc1c3-132">如果项本身的名称包含句点，因为它们被替代数字符号 （#）。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="fc1c3-133">假定任何项，直接在其名称中有数字符号。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="fc1c3-134">例如，完全限定的名称的`String`构造函数将`System.String.#ctor`。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
-   <span data-ttu-id="fc1c3-135">对于属性和方法，如果方法带有自变量，则后跟用括号括起来的自变量列表。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="fc1c3-136">如果没有任何自变量，则不会出现括号。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="fc1c3-137">确保自变量之间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-137">The arguments are separated by commas.</span></span> <span data-ttu-id="fc1c3-138">编码的每个自变量都直接遵循中的编码方式[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]签名。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-138">The encoding of each argument follows directly how it is encoded in a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc1c3-139">示例</span><span class="sxs-lookup"><span data-stu-id="fc1c3-139">Example</span></span>  
 <span data-ttu-id="fc1c3-140">下面的代码演示如何的 ID 字符串的类，并生成其成员。</span><span class="sxs-lookup"><span data-stu-id="fc1c3-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fc1c3-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc1c3-141">See Also</span></span>  
 [<span data-ttu-id="fc1c3-142">/doc</span><span class="sxs-lookup"><span data-stu-id="fc1c3-142">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="fc1c3-143">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="fc1c3-143">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
