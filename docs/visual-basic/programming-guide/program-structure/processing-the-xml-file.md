---
title: 处理 XML 文件
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 4230fd88b4b60c631135f5b7fb15f4b6272b5351
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347306"
---
# <a name="processing-the-xml-file-visual-basic"></a><span data-ttu-id="a9b27-102">处理 XML 文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9b27-102">Processing the XML File (Visual Basic)</span></span>
<span data-ttu-id="a9b27-103">编译器为代码（已标记以生成文档）中的每个构造生成一个 ID 字符串。</span><span class="sxs-lookup"><span data-stu-id="a9b27-103">The compiler generates an ID string for each construct in your code that is tagged to generate documentation.</span></span> <span data-ttu-id="a9b27-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md).) The ID string uniquely identifies the construct.</span><span class="sxs-lookup"><span data-stu-id="a9b27-104">(For information on how to tag your code, see [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md).) The ID string uniquely identifies the construct.</span></span> <span data-ttu-id="a9b27-105">Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item.</span><span class="sxs-lookup"><span data-stu-id="a9b27-105">Programs that process the XML file can use the ID string to identify the corresponding .NET Framework metadata/reflection item.</span></span>  
  
 <span data-ttu-id="a9b27-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span><span class="sxs-lookup"><span data-stu-id="a9b27-106">The XML file is not a hierarchical representation of your code; it is a flat list with a generated ID for each element.</span></span>  
  
 <span data-ttu-id="a9b27-107">编译器在生成 ID 字符串时应遵循以下规则：</span><span class="sxs-lookup"><span data-stu-id="a9b27-107">The compiler observes the following rules when it generates the ID strings:</span></span>  
  
- <span data-ttu-id="a9b27-108">字符串不得包含空格。</span><span class="sxs-lookup"><span data-stu-id="a9b27-108">No white space is placed in the string.</span></span>  
  
- <span data-ttu-id="a9b27-109">ID 字符串的第一部分标识被标识的成员类型，单个字符后跟一个冒号。</span><span class="sxs-lookup"><span data-stu-id="a9b27-109">The first part of the ID string identifies the kind of member being identified, with a single character followed by a colon.</span></span> <span data-ttu-id="a9b27-110">The following member types are used.</span><span class="sxs-lookup"><span data-stu-id="a9b27-110">The following member types are used.</span></span>  
  
|<span data-ttu-id="a9b27-111">字符</span><span class="sxs-lookup"><span data-stu-id="a9b27-111">Character</span></span>|<span data-ttu-id="a9b27-112">描述</span><span class="sxs-lookup"><span data-stu-id="a9b27-112">Description</span></span>|  
|---|---|  
|<span data-ttu-id="a9b27-113">N</span><span class="sxs-lookup"><span data-stu-id="a9b27-113">N</span></span>|<span data-ttu-id="a9b27-114">namespace</span><span class="sxs-lookup"><span data-stu-id="a9b27-114">namespace</span></span><br /><br /> <span data-ttu-id="a9b27-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span><span class="sxs-lookup"><span data-stu-id="a9b27-115">You cannot add documentation comments to a namespace, but you can make CREF references to them, where supported.</span></span>|  
|<span data-ttu-id="a9b27-116">T</span><span class="sxs-lookup"><span data-stu-id="a9b27-116">T</span></span>|<span data-ttu-id="a9b27-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span><span class="sxs-lookup"><span data-stu-id="a9b27-117">type: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`</span></span>|  
|<span data-ttu-id="a9b27-118">F</span><span class="sxs-lookup"><span data-stu-id="a9b27-118">F</span></span>|<span data-ttu-id="a9b27-119">field: `Dim`</span><span class="sxs-lookup"><span data-stu-id="a9b27-119">field: `Dim`</span></span>|  
|<span data-ttu-id="a9b27-120">P</span><span class="sxs-lookup"><span data-stu-id="a9b27-120">P</span></span>|<span data-ttu-id="a9b27-121">property: `Property` (including default properties)</span><span class="sxs-lookup"><span data-stu-id="a9b27-121">property: `Property` (including default properties)</span></span>|  
|<span data-ttu-id="a9b27-122">M</span><span class="sxs-lookup"><span data-stu-id="a9b27-122">M</span></span>|<span data-ttu-id="a9b27-123">method: `Sub`, `Function`, `Declare`, `Operator`</span><span class="sxs-lookup"><span data-stu-id="a9b27-123">method: `Sub`, `Function`, `Declare`, `Operator`</span></span>|  
|<span data-ttu-id="a9b27-124">E</span><span class="sxs-lookup"><span data-stu-id="a9b27-124">E</span></span>|<span data-ttu-id="a9b27-125">event: `Event`</span><span class="sxs-lookup"><span data-stu-id="a9b27-125">event: `Event`</span></span>|  
|<span data-ttu-id="a9b27-126">!</span><span class="sxs-lookup"><span data-stu-id="a9b27-126">!</span></span>|<span data-ttu-id="a9b27-127">错误字符串</span><span class="sxs-lookup"><span data-stu-id="a9b27-127">error string</span></span><br /><br /> <span data-ttu-id="a9b27-128">字符串的其余部分提供有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="a9b27-128">The rest of the string provides information about the error.</span></span> <span data-ttu-id="a9b27-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span><span class="sxs-lookup"><span data-stu-id="a9b27-129">The Visual Basic compiler generates error information for links that cannot be resolved.</span></span>|  
  
- <span data-ttu-id="a9b27-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span><span class="sxs-lookup"><span data-stu-id="a9b27-130">The second part of the `String` is the fully qualified name of the item, starting at the root of the namespace.</span></span> <span data-ttu-id="a9b27-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span><span class="sxs-lookup"><span data-stu-id="a9b27-131">The name of the item, its enclosing type(s), and the namespace are separated by periods.</span></span> <span data-ttu-id="a9b27-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span><span class="sxs-lookup"><span data-stu-id="a9b27-132">If the name of the item itself contains periods, they are replaced by the number sign (#).</span></span> <span data-ttu-id="a9b27-133">It is assumed that no item has a number sign directly in its name.</span><span class="sxs-lookup"><span data-stu-id="a9b27-133">It is assumed that no item has a number sign directly in its name.</span></span> <span data-ttu-id="a9b27-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span><span class="sxs-lookup"><span data-stu-id="a9b27-134">For example, the fully qualified name of the `String` constructor would be `System.String.#ctor`.</span></span>  
  
- <span data-ttu-id="a9b27-135">对于属性和方法，如果方法带有自变量，则后跟用括号括起来的自变量列表。</span><span class="sxs-lookup"><span data-stu-id="a9b27-135">For properties and methods, if there are arguments to the method, the argument list enclosed in parentheses follows.</span></span> <span data-ttu-id="a9b27-136">如果没有任何自变量，则不会出现括号。</span><span class="sxs-lookup"><span data-stu-id="a9b27-136">If there are no arguments, no parentheses are present.</span></span> <span data-ttu-id="a9b27-137">确保自变量之间用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a9b27-137">The arguments are separated by commas.</span></span> <span data-ttu-id="a9b27-138">The encoding of each argument follows directly how it is encoded in a .NET Framework signature.</span><span class="sxs-lookup"><span data-stu-id="a9b27-138">The encoding of each argument follows directly how it is encoded in a .NET Framework signature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9b27-139">示例</span><span class="sxs-lookup"><span data-stu-id="a9b27-139">Example</span></span>  
 <span data-ttu-id="a9b27-140">The following code shows how the ID strings for a class and its members are generated.</span><span class="sxs-lookup"><span data-stu-id="a9b27-140">The following code shows how the ID strings for a class and its members are generated.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="a9b27-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9b27-141">See also</span></span>

- [<span data-ttu-id="a9b27-142">-doc</span><span class="sxs-lookup"><span data-stu-id="a9b27-142">-doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
- [<span data-ttu-id="a9b27-143">如何：创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="a9b27-143">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
