---
title: 如何：将数据移入和移出变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bfda451cefff699561253910715d8450414b00ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650863"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="86726-102">如何：将数据移入和移出变量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86726-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="86726-103">通过将变量名称放在赋值语句的左侧，可以在变量中存储值。</span><span class="sxs-lookup"><span data-stu-id="86726-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="86726-104">将数据放在变量中</span><span class="sxs-lookup"><span data-stu-id="86726-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="86726-105">若要存储在变量中的一个值</span><span class="sxs-lookup"><span data-stu-id="86726-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="86726-106">在赋值语句的左侧使用的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="86726-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="86726-107">下面的示例设置变量的值`alpha`。</span><span class="sxs-lookup"><span data-stu-id="86726-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="86726-108">赋值语句右侧生成的值存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="86726-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="86726-109">从变量中获取数据</span><span class="sxs-lookup"><span data-stu-id="86726-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="86726-110">通过在表达式中包含的变量的名称，可以为其检索自定义变量的值。</span><span class="sxs-lookup"><span data-stu-id="86726-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="86726-111">从变量检索值</span><span class="sxs-lookup"><span data-stu-id="86726-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="86726-112">在表达式中使用的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="86726-112">Use the variable name in an expression.</span></span> <span data-ttu-id="86726-113">你可以使用变量任何可以使用的常量或文本，除中定义的常量值的表达式。</span><span class="sxs-lookup"><span data-stu-id="86726-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="86726-114">-或-</span><span class="sxs-lookup"><span data-stu-id="86726-114">-or-</span></span>  
  
-   <span data-ttu-id="86726-115">使用以下相等的变量名称 (`=`) 在赋值语句登录。</span><span class="sxs-lookup"><span data-stu-id="86726-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="86726-116">下面的示例读取该变量的值`startValue`，然后使用该变量的值`counter`在表达式中。</span><span class="sxs-lookup"><span data-stu-id="86726-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="86726-117">变量的值参与到表达式，就像将一个常数，并且然后存储在变量或赋值语句左侧的属性。</span><span class="sxs-lookup"><span data-stu-id="86726-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86726-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="86726-118">See Also</span></span>  
 [<span data-ttu-id="86726-119">变量</span><span class="sxs-lookup"><span data-stu-id="86726-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="86726-120">变量声明</span><span class="sxs-lookup"><span data-stu-id="86726-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="86726-121">对象变量</span><span class="sxs-lookup"><span data-stu-id="86726-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
