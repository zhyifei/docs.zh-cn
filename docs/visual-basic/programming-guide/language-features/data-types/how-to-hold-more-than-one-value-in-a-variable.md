---
title: 如何：在一个变量中保存多个值 (Visual Basic)
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
ms.openlocfilehash: 781f56c7e710f5130d821ca4796398379dfa4c6e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43456485"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="e5514-102">如何：在一个变量中保存多个值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5514-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="e5514-103">声明的变量存储多个值*复合数据类型*。</span><span class="sxs-lookup"><span data-stu-id="e5514-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="e5514-104">[复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)包括结构、 数组和类。</span><span class="sxs-lookup"><span data-stu-id="e5514-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="e5514-105">复合数据类型的变量可以包含基本数据类型和其他复合类型的组合。</span><span class="sxs-lookup"><span data-stu-id="e5514-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="e5514-106">结构和类可以包含代码，以及数据。</span><span class="sxs-lookup"><span data-stu-id="e5514-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="e5514-107">若要在变量中保存多个值</span><span class="sxs-lookup"><span data-stu-id="e5514-107">To hold more than one value in a variable</span></span>  
  
1.  <span data-ttu-id="e5514-108">确定想要使用变量的复合数据类型。</span><span class="sxs-lookup"><span data-stu-id="e5514-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2.  <span data-ttu-id="e5514-109">如果尚未定义的复合数据类型，定义它，以便你的变量可以使用它。</span><span class="sxs-lookup"><span data-stu-id="e5514-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    -   <span data-ttu-id="e5514-110">定义与结构[Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e5514-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    -   <span data-ttu-id="e5514-111">定义一个包含的数组[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e5514-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    -   <span data-ttu-id="e5514-112">使用定义类[Class 语句](../../../../visual-basic/language-reference/statements/class-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e5514-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3.  <span data-ttu-id="e5514-113">与将变量声明`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="e5514-113">Declare your variable with a `Dim` statement.</span></span>  
  
4.  <span data-ttu-id="e5514-114">变量名后面加`As`子句。</span><span class="sxs-lookup"><span data-stu-id="e5514-114">Follow the variable name with an `As` clause.</span></span>  
  
5.  <span data-ttu-id="e5514-115">请按照`As`关键字适当的复合数据类型的名称。</span><span class="sxs-lookup"><span data-stu-id="e5514-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5514-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5514-116">See Also</span></span>  
 [<span data-ttu-id="e5514-117">数据类型</span><span class="sxs-lookup"><span data-stu-id="e5514-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="e5514-118">类型字符</span><span class="sxs-lookup"><span data-stu-id="e5514-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [<span data-ttu-id="e5514-119">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="e5514-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="e5514-120">结构</span><span class="sxs-lookup"><span data-stu-id="e5514-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="e5514-121">数组</span><span class="sxs-lookup"><span data-stu-id="e5514-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="e5514-122">对象和类</span><span class="sxs-lookup"><span data-stu-id="e5514-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="e5514-123">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="e5514-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
