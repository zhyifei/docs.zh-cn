---
title: 如何：在一个变量 (Visual Basic 中) 中保存多个值
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: e2e1648ea508ecdd744adb8d2a4f7fdbc1e586c4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332256"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="0933d-102">如何：在一个变量 (Visual Basic 中) 中保存多个值</span><span class="sxs-lookup"><span data-stu-id="0933d-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="0933d-103">声明的变量存储多个值*复合数据类型*。</span><span class="sxs-lookup"><span data-stu-id="0933d-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="0933d-104">[复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)包括结构、 数组和类。</span><span class="sxs-lookup"><span data-stu-id="0933d-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="0933d-105">复合数据类型的变量可以包含基本数据类型和其他复合类型的组合。</span><span class="sxs-lookup"><span data-stu-id="0933d-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="0933d-106">结构和类可以包含代码，以及数据。</span><span class="sxs-lookup"><span data-stu-id="0933d-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="0933d-107">若要在变量中保存多个值</span><span class="sxs-lookup"><span data-stu-id="0933d-107">To hold more than one value in a variable</span></span>  
  
1. <span data-ttu-id="0933d-108">确定想要使用变量的复合数据类型。</span><span class="sxs-lookup"><span data-stu-id="0933d-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2. <span data-ttu-id="0933d-109">如果尚未定义的复合数据类型，定义它，以便你的变量可以使用它。</span><span class="sxs-lookup"><span data-stu-id="0933d-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    -   <span data-ttu-id="0933d-110">定义与结构[Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0933d-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    -   <span data-ttu-id="0933d-111">定义一个包含的数组[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0933d-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    -   <span data-ttu-id="0933d-112">使用定义类[Class 语句](../../../../visual-basic/language-reference/statements/class-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0933d-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3. <span data-ttu-id="0933d-113">与将变量声明`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="0933d-113">Declare your variable with a `Dim` statement.</span></span>  
  
4. <span data-ttu-id="0933d-114">变量名后面加`As`子句。</span><span class="sxs-lookup"><span data-stu-id="0933d-114">Follow the variable name with an `As` clause.</span></span>  
  
5. <span data-ttu-id="0933d-115">请按照`As`关键字适当的复合数据类型的名称。</span><span class="sxs-lookup"><span data-stu-id="0933d-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0933d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0933d-116">See also</span></span>

- [<span data-ttu-id="0933d-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="0933d-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0933d-118">类型字符</span><span class="sxs-lookup"><span data-stu-id="0933d-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="0933d-119">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="0933d-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="0933d-120">结构</span><span class="sxs-lookup"><span data-stu-id="0933d-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="0933d-121">数组</span><span class="sxs-lookup"><span data-stu-id="0933d-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="0933d-122">对象和类</span><span class="sxs-lookup"><span data-stu-id="0933d-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="0933d-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="0933d-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
